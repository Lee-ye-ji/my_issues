![image](https://user-images.githubusercontent.com/59958929/164444258-75f4cf64-26df-4de3-ad85-aadc3202c7bc.png)
이 오류는 map함수를 이용해서 부모 컴포넌트에서 자식 컴포넌트로 props를 보낼 때 나는 오류이다.
즉, [{...}, {...}, {...}] 해당되는 데이터를 map함수를 이용해서 {...} 객체 형식으로 props를 보낼 때 타입 오류에 해당되는 내용이다.

# Solved
`부모.tsx`
```tsx
function SearchPage(): JSX.Element {
  const repoData = [{...}, {...}, {...}]
  return (
      <Container>
        {repoData.map((item) => (
          <Card data={item} />
        ))}
      </Container>
  );
}
```

`자식.tsx`
```tsx
function Card({ data }: { data: RepositoryItem }): JSX.Element {
  return (
    <Wrapper>
      <Profile src={data.avatar} />
      <Content>
        <Title>{data.title}</Title>
        <User>{data.user}</User>
        <Desc>{data.desc}</Desc>
        <Date>{data.date}</Date>
        <Save>저장하기</Save>
      </Content>
    </Wrapper>
  );
}
```

나는 자식 컴포넌트에서 (data: RepositoryItem)와 같이 데이터 타입을 지정했는데 { data }: { data: RepositoryItem }처럼 작성을 해야된다!!!

https://velog.io/@ye-ji/Error-IntrinsicAttributes-props-in-React-Typescript-component-6nak5n7m
