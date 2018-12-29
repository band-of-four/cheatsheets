## Директивы

`ng-app` определяет AngularJS приложение.

`ng-model` связывает значения элементов ввода HTML (input, select, textarea) с данными приложения.

`ng-bind` связывает данные приложения с отображением в HTML.

 `ng-init` инициализирует переменные приложения AngularJS.

```html
<!DOCTYPE html>
<html>
<script src="https://ajax.googleapis.com/ajax/libs/angularjs/1.6.4/angular.min.js"></script>
<body>

<div ng-app="" ng-init="firstName='John'">
  <p>Name: <input type="text" ng-model="name"></p>
  <p ng-bind="name"></p>
</div>

</body>
</html>
```

## Выражения

 указываются в фигурных скобках: {{выражение}}

## Приложения

AngularJS __модули__ определяют AngularJS приложения.

AngularJS __контроллеры__ управляют AngularJS приложением.

(Модуль представляет собой контейнер для контроллеров приложений. Контроллеры всегда принадлежат к модулю.)

Директива `ng-app` определяет приложение, директива `ng-controller` определяет контроллер.

```js 
var app = angular.module('myApp', []);
app.controller('myCtrl', function($scope) {
    $scope.firstName = "John";
    $scope.lastName = "Doe";
});
```

```html
First Name: <input type="text" ng-model="firstName"><br>
Last Name: <input type="text" ng-model="lastName"><br>
```

## Компоненты

```js
@Component({
    selector: 'my-app',
    styles: [`
        input.ng-touched.ng-invalid {border:solid red 2px;}
        input.ng-touched.ng-valid {border:solid green 2px;}
    `],
    template: `<form #myForm="ngForm" novalidate>
                    <div class="form-group">
                        <label>Имя</label>
                        <input class="form-control" name="name" [(ngModel)]="name" required />
                    </div>
                    <div class="form-group">
                        <label>Email</label>
                        <input class="form-control" name="email" ngModel 
                            required email />
                    </div>
                    <div class="form-group">
                        <label>Телефон</label>
                        <input class="form-control" name="phone" ngModel 
                            required pattern="[0-9]{10}" />
                    </div>
                    <div class="form-group">
                        <button [disabled]="myForm.invalid"
                                class="btn btn-default" (click)="submit(myForm)">Добавить</button>
                    </div>
                </form>
                <div>Имя: {{myForm.value.name}}</div>
                <div>Email: {{myForm.value.email}}</div>`
})
export class AppComponent { 
 
    submit(form: NgForm){
        console.log(form);
    }
}
```

# Задание: Написать на angular проверку авторизирован ли пользователь. Если нет, то отправить ему форму для авторизации

```js
var authorizationModule = angular.module('authorizationModule', []);
 
authorizationModule.controller('loginCtrl', ['$scope', 'authorizationFactory', '$location', 
function($scope, authorizationFactory, $location){
  $scope.loginClick = function() {
    if (authorizationFactory.login($scope.login, $scope.pass)) {
    
    } else {
      $location.path('/login.html');
    }
  }
}]);
```

# Задание:  angular компонент который позволяет чето там постить в социальных сетях типа вк фейсбук

```js
// ну, я попыталась
@Component({
    selector: 'app-add-post',
    templateUrl: './add-post.component.html',
    styleUrls: ['./add-post.component.css']
    template: `<form #myForm="ngForm" novalidate>
                    <div class="form-add-post">
                        <label>Текст</label>
                        <input class="form-control" name="name" [(ngModel)]="name" required />
                    </div>
                </form>
                <div>Текст: {{myForm.value.text}}</div>
})
export class AppComponent { 
 
    submit(form: NgForm){
        console.log(form);
    }
}
```
