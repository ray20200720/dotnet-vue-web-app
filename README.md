# dotnet-vue-web-app
use vue with dotnet

### Create Project

``` bash
dotnet new webapp -o DotnetVueWebApp
```

### Modify `Index.cshtml`

1. include vue

``` html
<script src="https://unpkg.com/vue@3/dist/vue.global.js"></script>
```
2. modify `<div class="text-center">` as below

``` html
<div id="app" class="text-center">
    <h1 class="display-4">Welcome</h1>
    <p>Learn about <a href="https://docs.microsoft.com/aspnet/core">building Web apps with ASP.NET Core</a>.</p>
    <p>{{ message }} <a :href="[url]">Vue</a>.</p>
    <button v-on:click="count++">{{ count }}</button>
    <p>Has published books:</p>
    <span>{{ author.books.length > 0 ? 'Yes' : 'No' }}</span>
</div>
```
3. add JavaScript as below

``` js
<script>
  const { createApp } = Vue
  createApp({
    data() {
      return {
        url: 'https://vuejs.org/',
        message: 'Learn about ',
        count: 0,
        author: {
            name: 'John Doe',
            books: [
                'Vue 2 - Advanced Guide',
                'Vue 3 - Basic Guide',
                'Vue 4 - The Mystery'
            ]
        }
      }
    }
  }).mount('#app')
</script>
```

4. execute `dotnet run`

5. browse `http://localhost:5500` by browser

### Others

If you want to download vue.global.js to local side and use it by local.
Please save vue.global.js in the folder `wwwroot\js\` and modify the js
`<script src="~/js/vue.global.js"></script>` of `Index.cshtml` 
