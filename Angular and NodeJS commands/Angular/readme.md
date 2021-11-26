# Setup and useful commands
**Install the Angular CLI**
```console
npm install -g @angular/cli
```
**Create a workspace and initial application**
```console
ng new app-name --skip-tests=true
```
**Run the application and open it on the browser**
```console
ng serve --open
```
**Add a dependency and save it on the config file package.json**
```console
npm install package@version
```
**Exemple add Bootstrap to a project**
```console
npm install bootstrap@latest
```
Configure angular.json
```json
"styles": [
  "node_modules/bootstrap/dist/css/bootstrap.min.css",
  "styles.scss"
]
```
Import directly in src/style.css or src/style.scss
```javascript
@import '~bootstrap/dist/css/bootstrap.min.css';
```

# Angular

## **Components**
Components are the main building block for Angular applications. Each component consists of:
- An HTML template that declares what renders on the page
- A Typescript class that defines behavior
- Optionally, CSS styles applied to the template
### **Create a component**
`ng generate component component-name` or `ng g c component-name`

### **Data binding**
### **String Interpolation and property binding (code TS -> HTML Template)**
On the TS class:
```javascript
export class component-name implements onInit {
    let varName = "value";
    let isDisabled = true;
    function functionName(){
        return "value";
    }
}
```
On the HTML template:
```html
{{varName}} or {{functionName()}}
<button [disabled]="isDisabled">button</button>  <!-- [proprety] -->
```
### **Event binding (HTML Template -> Code TS)**
On the TS class:
```javascript
export class component-name implements onInit {
    function onClick(){
        // do something
    }
}
```
On the HTML template:
```html
<button (click)="onClick()">button</button>  <!-- (event) -->
```
### **Two way binding (HTML Template <-> Code TS)**
on app.module.ts:
```javascript
import { FormsModule } from '@angular/forms'
//...
imports:[
    FormsModule   /* add on imports array */
]
//...
```
on TS class: 
```javascript
export class component-name implements onInit {
    let varName = "value"
}
```
On the HTML template:
```html
{{varName}}   <!-- the value displayed changes when changing input value -->
<input type="text" [(ngModel)]="varName"> 
```
### **Pass data from parent to childrens using new selector properties**
on parent component TS class
```javascript
export class AppComponent {
  let varName = 'value';
```
on parent component HTML template
```html
    <componenet-selector [propretyName]="varName" ></componenet-selector>
```
on child component TS class 
```javascript
export class component-name implements OnInit {
 {
  @Input() propretyName : <type>;
 }
```
on child component HTML template
```html
    {{propretyName}}
```

## **Directives**
### **Structural directives**
#### **NgIf**
```html
<div *ngIf="showMessage === true">    <!-- condition or function that returns true or false -->
   show message 
</div>
```
#### **NgFor**
```html
<ul>
    <li *ngFor="let elt of arr">{{elt}}</li>  <!-- the array can be an array of primitive types or an array of objects -->
</ul>
```
### **Attribute directives**
#### **NgStyle**
```html
<div [ngStyle]="{color : functionName()}"> <!-- ngStyle takes an object, functionName is defined in TS class-->
   show message 
</div>
```
#### **NgClass**
```html
<div 
    [ngClass]="{            
        'form-group' : true,
        'col': column === true,
        'row': isRow()
        }"> <!-- ngClass takes an object also-->
   show message 
</div>

```

## **Transforming Data Using Pipes**
Pipes are simple functions to use in template expressions to accept an input value and return a transformed value.
```html
<p>{{ varName | date:'yyyy-MM-dd' }}</p>
<p>{{ varName | async }}</p> <!-- for asynchronous data -->
```


## **Services**
Dependencies are services or objects that a class needs to perform its function. Dependency injection is a design pattern in which a class requests dependencies from external sources rather than creating them.
<br>To generate a service:
```console
ng generate service service-name
```
To use a service in all the apllication, in the app.module.ts :
```javascript
import {servicClasseName } from "./...";

providers :[
    serviceName
]
```
To use the instance of the service in a component:
```javascript
varName;
constructor(private service : ServiceClassName){}
ngOnIni(){
    varName = service.varName ;
}
```

## Routing
in app.module.ts 
```javascript
const appRoutes: Routes = [
    {path: 'pathName', componenent: componentName }
]

imports: [
    RouterModule.forRoot(appRoutes)
```

## Observales
An observable is an object that sends data in time, each observables is associated with an observer a block of code that will be executed each time the observable sends an information.