# 간단한 게시판 만들기

## Next.js 프로젝트 세팅

```
npx create-next-app board
cd board
```

- typescript 사용 안함
- eslint 사용함
- app route 사용안함

## Prisma 세팅

### 패키지 설치 및 설정파일 생성

```
npm install -D prisma
npm install @prisma/client
npx prisma init
```

prisma 폴더의 schema.prisma 내용 작성

경로: `prisma/schema.prisma`
```
generator client {
  provider = "prisma-client-js"
}

datasource db {
  provider = "sqlite"
  url      = "file:./dev.db"
}

model Board {
  id    Int     @id @default(autoincrement())
  title String
  posts Post[]  @relation("BoardToPost")
}

model Post {
  id      Int    @id @default(autoincrement())
  title   String
  content String
  boardId Int
  board   Board  @relation("BoardToPost", fields: [boardId], references: [id])
}

```


### 위에서 작성한 스키마를 바탕으로 client 생성

```
npx prisma generate
```


### 마이그레이션 파일 생성

```
npx prisma migrate dev
```


### 스튜디오 실행

구름ide 에서는 동작하지 않음. 로컬에서 실행

```
npx prisma studio
```

## Board 관련 기능 생성


## Post 관련 기능 생성
