# Angular2 Order Pipe [![Build Status](https://travis-ci.org/VadimDez/ng2-order-pipe.svg?branch=master)](https://travis-ci.org/VadimDez/ng2-order-pipe)

> Order your collection by a field

<img src="https://cloud.githubusercontent.com/assets/3748453/22164327/08764608-df57-11e6-9c90-075aeca26fd6.gif" width="300">

### Demo page
[https://vadimdez.github.io/ng2-order-pipe/](https://vadimdez.github.io/ng2-order-pipe/)

## Install

```
npm install  ng2-order-pipe --save
```

## Usage

##### In HTML template

```html
{{ collection | orderBy: expression : reverse }}
```

### Arguments

| Param | Type | Details |
| --- | --- | --- |
| collection | `array` | The collection to sort |
| expression  | `string` | The key to compare |
| reverse *(optional)* | `boolean`| Reverse sorting order |

Import `Ng2FOrderModule` to your module

```ts
import { NgModule } from '@angular/core';
import { BrowserModule  } from '@angular/platform-browser';
import { AppComponent } from './app';

import { Ng2FOrderModule } from 'ng2-order-pipe';

@NgModule({
  imports: [BrowserModule, Ng2FOrderModule],
  declarations: [AppComponent],
  bootstrap: [AppComponent]
})
export class AppModule {}

```

And use pipe in your component

```ts
import { Component } from '@angular/core';

@Component({
  selector: 'example',
  template: `
    <div>
      <ul>
        <li *ngFor="let item of array | orderBy: order">
          {{ item.name }}
        </li>
      </ul>
    </div>  
  `
})

export class AppComponent {
  array: any[] = [{ name: 'John'} , { name: 'Mary' }, { name: 'Adam' }];
  order: string = 'name';
}
```

## License

[MIT](https://tldrlegal.com/license/mit-license) © [Vadym Yatsyuk](https://github.com/vadimdez)
