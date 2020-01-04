# Web API

### Запрос данных к API \(axios\)

{% hint style="info" %}
more here [https://github.com/Turanchoks/use-axios-request](https://github.com/Turanchoks/use-axios-request)
{% endhint %}

В самом простом сценарии нужно обработать следующие состояния:

* процесс получения данных \(isFetching\)
* данные успешно получены \(responseData\)
* ошибка получения данных \(error\)
* отмена запроса, если в процессе его выполнения поменялись параметры запроса, и нужно отправить новый
* отмена запроса, если данного компонента больше нет в DOM

Напишем дефолтный state и функцию \(reducer\), которая меняет state в зависимости от результата запроса: success / error.

```text
const useRequest1 = url => {
  const [state, dispatch] = React.useReducer(reducer, defaultState);

  React.useEffect(() => {
    const source = axios.CancelToken.source();
    axios
      .get(url, {
        cancelToken: source.token
      })
      .then(response => {
        dispatch({ type: "fetched", payload: response.data });
      })
      .catch(error => {
        dispatch({ type: "error", payload: error });
      });
    return source.cancel;
  }, [url]);

  return [state];
};
```

По url из используемого компонента получаем данные — axios.get\(\). Обрабатываем success и error, меняя state через dispatch\(action\). Возвращаем state в компонент. И не забываем отменить запрос в случае изменения url или если компонент удалился из DOM.

```text
const AvatarWithHook1 = ({ username }) => {
  const [state] = useRequest(`https://api.github.com/users/${username}`);

  if (state.isFetching) {
    return "Loading";
  }

  if (state.error) {
    return "Error";
  }

  return <img src={state.responseData.avatar_url} alt="avatar" />;
};
```

