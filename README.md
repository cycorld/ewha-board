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

```
npm install -D prisma
npm install @prisma/client
npx prisma init
```

prisma 폴더의 schema.prisma 내용 작성

```
npx prisma generate
```

위에서 작성한 스키마를 바탕으로 client 생성

```
npx prisma migrate dev
```

마이그레이션 파일 생성

```
npx prisma studio
```
