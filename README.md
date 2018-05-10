# Demo of AngularCompilerPlugin file replacements issue

## Details

I've added the following `fileReplacement` to the `production` configuration in `angular.json`:
```
{
  "replace": "src/app/app.component.css",
  "with": "src/app/app.component.prod.css"
}
```

The file replacement is not respected and `app.component.css` is included in the bundle instead of its replacement - `app.component.prod.css`.

## Steps to reproduce

```
npm i
ng serve --prod
```

The color of the text should be purple as specified in `app.component.prod.css`. It's pink instead - as specified in `app.component.css`.

