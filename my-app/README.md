Week24

1. Кратко опишите основные отличия state от props. props передаётся в компонент (служат как параметры функции), в то время как state находится внутри компонента (по аналогии с переменными, которые объявлены внутри функции). Props нельзя изменять, а state возможно
2. Какую ошибку я допустила в следующем коде и как её исправить:
   handleChange = () => {
   const chechedArr = this.state.arr; // [1,2,3]
   chechedArr.push(5); // [1,2,3,5]
   this.setState({
   arr: chechedArr,
   });
   };
   Добавить spread syntax и создать новый массив

handleChange = () => {
const chechedArr = […this.state.arr}; // [1,2,3]
chechedArr.push(5); // [1,2,3,5]
this.setState({
arr: chechedArr,
});
};

3. Можно ли повесить на один элемент несколько обработчиков событий?
   Да
4. Каким образом можно изменить state?C помощью функции setState()
5. Попробуйте предсказать, какие сообщения будут в консоли, и объяснить результат:
   handleChange = () => {
   console.log(this.state.checked) //#1 false
   this.setState({
   checked: !this.state.checked, //true
   });
   console.log(this.state.checked) //#2 ?
   };  
   False, т.к setState работает асинхронно

6. Какими способами можно задать функцию handleChange и какой из них является самым правильным? Внутри классового компонента, с помощью хука useState
7. Чем отличаются классовые и функциональные компоненты? Какие из них предпочтительнее в 2021 году? Главное отличие классового компонента от функционального это возможность хранить внутреннее состояния. Классовый компонент должен содержать метод render(), который возвращает React-элемент. Доступ к props осуществляется через this
8. Есть ли this в функциональных компонентах? Как можно получить доступ к нему? Вместо this в функциональных компонентах использются hooks ex useState
9. Можно ли использовать props и state одновременно? Да, через props можно получать данные из внешнего источника, а states управляет внутренним состоянием компонента
10. Где можно задать state без использования команды this.setState? Через функциональный компонент использую useState
11. Может ли состояние классового компонента не быть объектом? А функционального? Классовый компонент всегда объект, функциональный может быть объект, примитив (строка, цифра, булеан)
12. Способны ли функциональные компоненты самостоятельно хранить состояние? Да, с помощью useState
13. Как использовать хуки в классовых компонентах? Хуки не могут быть использованы внутри классовых компонентов
14. А как задать начальное состояние props, если они ещё не были переданы?
    Class Component extends React.Component {
    Constructor(props){
    Super(props)
    This.state = {}
    }}
