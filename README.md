# Joke-API
아재개그 120개 - API 서버 풀 코드 (Fast API)

## API 사용법
```
GET /quiz/random
→ { "id": 123, "question": "가장 친한 코끼리는?", "answer": "베프" }

GET /quiz/{id}
→ { "id": 123, "question": "...", "answer": "..." }
```

## 서버 실행
`uvicorn api:app --reload --port 8000`

## 디스코드 봇 연동 방법 (예제 코드)
```
import aiohttp # 필수

async def sexy_joke():
    async with aiohttp.ClientSession() as session:
        async with session.get("http://localhost:8000/quiz/random") as resp:
            if resp.status == 200:
                return await resp.json()
            return None
```
