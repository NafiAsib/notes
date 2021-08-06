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

