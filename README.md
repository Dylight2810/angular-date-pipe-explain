# 🔥 Angular Date Pipe Explain
👀 Example explain how to use Angular built-in Date Pipe with custom config and compare it with Intl DateTimeFormat

## Table of contents
- ❔ How to use Angular Built-in Date Pipe ?
- ✅ Explain some pre-defined format options
- ⭐ Using Date Pipe with custom format options
- 🔧 Register Locale data for Angular Application

## 1. How to use Angular Built-in Date Pipe ?
> Date Pipe is a built-in pipes for typical data transformations of Angular Framework. So you can use this pipe after init Angular Project without install any library

```typescript
import { Component } from '@angular/core';

@Component({
  selector: 'my-app',
  template: '<div>{{ myDate | date: 'h:mma dd, MMMM, yyyy':'GTM' }}</div>',
  styleUrls: [ './app.component.css' ]
})
export class AppComponent  {
  myDate = new Date()
}
```
## 2. Explain some pre-defined format options
> Angular Date Pipe provides some defined format for developer

| Format | Description | Example result |
| --- | --- | --- |
| `'short'` | 'M/d/yy, h:mm a' | 6/15/15, 9:03 AM

Read more at: https://angular.io/api/common/DatePipe#pre-defined-format-options

## 3. Using Date Pipe with custom format options
> I just explain some config that I prefer to use in bellow

| Format | Note | Description | Example result |
| :-----: | --- | --- | --- |
| `yyyy` | `y`not `Y` | Format year, each `y` character is present for 1 digit in the year number | EX: `yyyy - 2022`, `yyy - 022`, `yy - 22`
| `MMMM` | `M`not `m` | Format month | EX: `MMMM - tháng 9`, `MMM - thg 9`, `MM - 09`, `M - 9`
| `LLLL` | `L`not `l` | Format month like M but in some locale case first Month character will be Uppercase | EX: `LLLL - Tháng 9`, `LLL - Thg 9`, `LL - 09`
| `h` | | Format hour from 0h - 12h, `hh` auto add zero padded after hour | EX: `h - 9, hh - 09`, `h - 12, hh - 12`
| `H` | | Format hour from 0h - 23h, `HH` auto add zero padded after hour | EX: `h - 9, hh - 09`, `h - 22, hh - 22`
| `m` | | Format minute, `mm` auto add zero padded after hour | EX: `m - 2, mm - 02`, `m - 12, mm - 12`
| `s` | | Format second, `hh` auto add zero padded after hour | EX: `s - 1, s - 01`, `s - 11, ss - 11`

Read more at: https://angular.io/api/common/DatePipe#custom-format-options

## 4. Register Locale data for Angular Application
```typescript
import { BrowserModule } from '@angular/platform-browser';
import { AppComponent } from './app.component';

import { registerLocaleData } from '@angular/common';
import localeDe from '@angular/common/locales/de';
import localeVi from '@angular/common/locales/vi';

// Register more locale for transformation pipe in Angular
registerLocaleData(localeDe);
registerLocaleData(localeVi);

@NgModule({
  imports: [BrowserModule],
  declarations: [AppComponent],
  bootstrap: [AppComponent],
})
export class AppModule {}
```

### 👀 Document for Create Beautiful and Usage Readme file: 
> https://docs.github.com/en/github/writing-on-github


