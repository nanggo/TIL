
# DI Container

ViewModel을 initTask에서 Create해줄 때 framework service 중에 하나를 주입해주려 했다.
기존에는 파라미터로 원하는 서비스들을 넘겨줘서 이용했었는데 아닌 것 같아서 의존성을 주입해주었다.

주입한 서비스를 바로 이용하려 했는데 아래와 같은 에러가 나서 찾아보았다.

>Assertion Failed: Attempting to lookup an injected property on an object without a container, ensure that the object was instantiated via a container.

빛과 같은 [StackOverflow](https://stackoverflow.com/questions/52841900/how-can-i-inject-a-service-in-adapter-emberjs)에 답이 있었다. [Lux](https://stackoverflow.com/questions/52841900/how-can-i-inject-a-service-in-adapter-emberjs#comment92603490_52841900)라는 유저가 말한 바와 같이 DI Container를 이용하지 않아서 발생한 문제였다. 직접 object를 `.create()`로 만들어 줬다면 [`OwnerInjection`](https://api.emberjs.com/ember/3.5/classes/ApplicationInstance/methods/ownerInjection?anchor=ownerInjection)을 이용해서 object에 owner를 제공해줘야 한다.

```javascript
import { getOwner } from '@ember/application';

const owner = getOwner(this);
const viewModel = ViewModel.create(owner.ownerInjection(), {});
```

[여기](https://stackoverflow.com/questions/37843461/ember-inject-service-into-ember-utility)를 보면 `Ember.inject.service`의 동작 원리를 알 수 있다. (이 역시 Lux의 답변)