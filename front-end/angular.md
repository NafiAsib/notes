# Angular



* Change property value dynamically with every keypress. _backspace counts too_

```typescript
<input type="text" [ngModel]="property" (ngModelChange)="onValueChange($event)" />
{{property}}


onValueChange(newValue) {
  property = newValue;
  console.log(newValue)
}
```

#### Resources

* [Official Doc](https://angular.io/docs)

#### Styles

* [ESLint Angular](https://github.com/angular-eslint/angular-eslint)
* [ESLint w/ Prettier & AirBnB styleguide](https://dev.to/bzvyagintsev/migrate-angular-app-to-eslint-with-prettier-airbnb-styleguide-husky-and-lint-staged-862) - I prefer json config over js

