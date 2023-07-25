## `useTab`

- ### 버튼을 누르면 그에 맞는 내용을 나오게 하는 기능

```jsx
// 예시 데이터
const content = [
  {
    tab: "Section 1",
    content: "I'm content of section 1",
  },
  {
    tab: "Section 2",
    content: "I'm content of section 2",
  },
];

const useTab = (initialTab, allTabs) => {
  const [currentIndex, setCurrentIndex] = useState(initialTab);

  if (!allTabs || !Array.isArray(allTabs)) {
    //allTabs가 배열인지 그리고 값이 들어 있는지를 확인한다
    return;
  }

  return {
    currentItem: allTabs[currentIndex],
    changeItem: setCurrentIndex,
  };
};

const App = () => {
  const { currentItem, changeItem } = useTab(0, content); // 기본 값으로 처음 배열 인덱스 번호와 배열을 보낸다
  return (
    <div className="App">
      {content.map((section, index) => {
        return (
          <button
            onClick={() => {
              changeItem(index); //changeItem에 index번호를 넣어서 실행하면 useTabs 안에 있는 setCurrentIndex(index)와 똑같이 작동한다
            }}
          >
            {section.tab}
          </button>
        );
      })}
      {currentItem.content}
    </div>
  );
};

export default App;
```
