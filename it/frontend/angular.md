# Angular

## Summary

- old Angular: AngularJS (= Angular 1)
- backed by Google
- TypeScript-based
- component-based

## Architecture

- NgModule
  - capsulate modules
- Directive
  - have an effect in rendered view
- View
  - render
- Component
  - View + Directive
- Pipe
  - filter & process values
- Service
  - functional code, e.g.call service

## Angular CLI

```bash
ng new my-app
cd my-app
ng serve
ng generate component XY
ng generate service XY
```

## Components

- selector: to reference
- template: html template
- style

```javascript
@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.less']
})
```

- interpolation
  - `{{ message }}`
- change detection
- dependency injection
  - constructor injection

### Lifecycle

- ngOnInit
  - before first rendering
  - `implements OnInit`
- ngOnDestroy
- ngOnChanges

### Data Binding

- `[item]`
- @Input()

### Event Binding

- `(click)`
- @Output()

### Directives

- `*ngIf`
- `*ngFor`
- `[(ngModel)]`: two-way data binding

### Pipes

- to convert values
- `ng generate pipe`

### Content Projection

- e.g to define a header
- `<ng-content />`

## Routing

- path-component associations in app-module
- redirect
- wildcard
- params: `books:/:bookName`
- nested routes
- navigate programatically
  - `router.navigate()`

## Testing

### Unit

- [Karma](https://karma-runner.github.io/latest/index.html)

### E2E

- [Protactor](http://www.protractortest.org/#/)