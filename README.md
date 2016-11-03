
# Angular 2 : Typescript component for Destroy Subscribers

Installation
--------------------------------------

Install it from npm:

```bash
npm install ng2-destroy-subscribers
```

Usage
--------------------------------------


### Подключение

Подключение декоратора

```html
import {DestroySubscribers} from "ng2-destroy-subscribers";

@Component({
  ...
})
@DestroySubscribers({
  addSubscribersFunc: 'addSubscribers',
  removeSubscribersFunc: 'removeSubscribers',
  initFunc: 'ngOnInit',
  destroyFunc: 'ngOnDestroy',
})
export class TestComponent {
  public subscribers: any = {};
  
  addSubscribers() {
    this.subscribers.testSubscriber = Observable.of('true')
    .subscribe(response => {
      console.log(response);
    })
  }
}
```

- `subscribers` - Обьект в котором хранятся все подписчики
- `addSubscribersFunc` - Функция в которой мы подписываемся на стримы (по умолчанию - addSubscribers)
- `removeSubscribersFunc` - Функция в которой автоматически удаляются подписчики (по умолчанию - removeSubscribers)
- `initFunc` - Функция которая вызывается при срабатывании конструктора (по умолчанию - ngOnInit)
- `destroyFunc` - Функция которая вызывается при срабатывании деструктора (по умолчанию - ngOnDestroy)

