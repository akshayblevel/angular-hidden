# angular-hidden

my-component.component.ts

```js
import { Component, OnInit } from '@angular/core';

@Component({
  selector: 'app-my-component',
  templateUrl: './my-component.component.html',
  styleUrls: ['./my-component.component.css']
})
export class MyComponentComponent implements OnInit {
  constructor() {}

  ngOnInit() {}
  employees = [
    {
      name: 'Akshay Patel'
    },
    {
      id: 2,
      name: 'Panth Patel'
    }
  ];
}
```
my-component.component.html

```html
<div *ngFor="let employee of employees">
  <div [hidden]="!employee.id">
    {{employee.id}} <br/>
  </div>
  {{employee.name}}
  <hr />
</div>
```

app.module.ts

```js
import { NgModule } from '@angular/core';
import { BrowserModule } from '@angular/platform-browser';
import { FormsModule } from '@angular/forms';

import { AppComponent } from './app.component';
import { MyComponentComponent } from './my-component/my-component.component';

@NgModule({
  imports: [BrowserModule, FormsModule],
  declarations: [AppComponent, MyComponentComponent],
  bootstrap: [AppComponent]
})
export class AppModule {}
```

app.component.html

```html
<app-my-component></app-my-component>
```


