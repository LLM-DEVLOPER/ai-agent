# FastAPI 后端开发面试知识点

这份文档覆盖 FastAPI 后端开发的核心知识点，从路由设计、依赖注入、到流式响应和后台任务，每个环节都有面试常考的技术细节。

---

## 1. FastAPI 核心特性与优势

**面试官可能会问：** FastAPI 相比 Flask/Django 有什么优势？

**回答要点：**

FastAPI 是现代 Python Web 框架，基于 Starlette（ASGI）和 Pydantic（数据验证），核心优势：

| 特性 | FastAPI | Flask | Django |
|------|---------|-------|--------|
| 性能 | 极高（异步 ASGI） | 中等（同步 WSGI） | 中等（同步 WSGI） |
| 类型安全 | 原生支持（Pydantic） | 无 | 部分支持 |
| 自动文档 | 自动生成（OpenAPI） | 需手动 | 需手动 |
| 异步支持 | 原生支持 | 需扩展 | 3.1+ 支持 |
| 学习曲线 | 低 | 低 | 高 |

**核心优势：**
1. **性能接近 Go/Node.js**：异步 I/O + 高效序列化
2. **自动数据验证**：Pydantic 模型自动验证请求体
3. **自动 API 文档**：访问 `/docs` 即可看到 Swagger UI
4. **类型提示驱动**：IDE 自动补全，减少运行时错误

---

## 2. 路由与请求处理

**面试官可能会问：** FastAPI 的路由装饰器有哪些？路径参数和查询参数怎么区分？

**回答要点：**

FastAPI 通过装饰器定义路由，支持路径参数、查询参数、请求体等多种参数类型。

```python
from fastapi import FastAPI, Query, Path, Body
from pydantic import BaseModel

app = FastAPI()

# 路径参数（必需）
@app.get("/users/{user_id}")
async def get_user(user_id: int = Path(..., gt=0)):
    return {"user_id": user_id}

# 查询参数（可选）
@app.get("/items/")
async def list_items(skip: int = 0, limit: int = Query(10, le=100)):
    return {"skip": skip, "limit": limit}

# 请求体（Pydantic 模型）
class User(BaseModel):
    name: str
    email: str

@app.post("/users/")
async def create_user(user: User):
    return {"name": user.name, "email": user.email}
```

**面试一句话总结：** 路径参数用 `{param}`，查询参数用函数参数默认值，请求体用 Pydantic 模型，FastAPI 自动验证和序列化。

---

## 3. 依赖注入系统

**面试官可能会问：** FastAPI 的依赖注入是什么？有什么用？

**回答要点：**

依赖注入（Dependency Injection）是 FastAPI 的核心特性，通过 `Depends()` 声明依赖关系，框架自动解析和注入。

```python
from fastapi import Depends, HTTPException

# 定义依赖
async def get_db():
    db = Database()
    try:
        yield db
    finally:
        db.close()

async def get_current_user(token: str = Header(...)):
    user = verify_token(token)
    if not user:
        raise HTTPException(status_code=401)
    return user

# 使用依赖
@app.get("/users/me")
async def read_user_me(
    current_user: User = Depends(get_current_user),
    db: Database = Depends(get_db)
):
    return current_user
```

**核心价值：** 代码复用、关注点分离、易于测试（可以 mock 依赖）。

---

## 4. 流式响应（SSE）

**面试官可能会问：** FastAPI 怎么实现流式输出？和普通响应有什么区别？

**回答要点：**

流式响应通过 `StreamingResponse` 实现，适合 AI 生成、大文件传输等场景。

```python
from fastapi.responses import StreamingResponse
import asyncio

async def generate_tokens():
    for i in range(10):
        yield f"data: Token {i}\n\n"
        await asyncio.sleep(0.1)

@app.get("/stream")
async def stream_response():
    return StreamingResponse(
        generate_tokens(),
        media_type="text/event-stream"
    )
```

**面试一句话总结：** 流式响应用 `StreamingResponse` + 生成器，适合 AI 生成和大数据传输，降低首字节延迟。

---

## 5. 中间件与异常处理

**面试官可能会问：** FastAPI 的中间件怎么写？异常处理怎么做？

**回答要点：**

中间件用于处理请求/响应的全局逻辑（如日志、CORS、认证）。

```python
from fastapi import Request
from fastapi.middleware.cors import CORSMiddleware

# CORS 中间件
app.add_middleware(
    CORSMiddleware,
    allow_origins=["*"],
    allow_methods=["*"],
    allow_headers=["*"],
)

# 自定义中间件
@app.middleware("http")
async def log_requests(request: Request, call_next):
    start_time = time.time()
    response = await call_next(request)
    duration = time.time() - start_time
    print(f"{request.method} {request.url} - {duration:.2f}s")
    return response

# 异常处理
@app.exception_handler(ValueError)
async def value_error_handler(request: Request, exc: ValueError):
    return JSONResponse(status_code=400, content={"error": str(exc)})
```

**面试一句话总结：** 中间件用 `@app.middleware` 或 `add_middleware`，异常处理用 `@app.exception_handler`，实现全局逻辑复用。

---

## 6. 后台任务

**面试官可能会问：** FastAPI 怎么处理后台任务？

**回答要点：**

后台任务用 `BackgroundTasks`，在响应返回后异步执行，不阻塞用户请求。

```python
from fastapi import BackgroundTasks

def send_email(email: str, message: str):
    # 耗时操作
    time.sleep(5)
    print(f"Email sent to {email}")

@app.post("/send-notification/")
async def send_notification(
    email: str,
    background_tasks: BackgroundTasks
):
    background_tasks.add_task(send_email, email, "Hello")
    return {"message": "Notification queued"}
```

**面试一句话总结：** `BackgroundTasks` 用于轻量级后台任务，重任务用 Celery/RQ。

---





