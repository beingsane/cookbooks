# [Grunt Contrib Copy](https://www.npmjs.org/package/grunt-contrib-copy)

```bash
npm install grunt-contrib-copy --save-dev
```

```js
grunt.loadNpmTasks('grunt-contrib-copy');
```

```js
// Copies remaining files to places other tasks can use
copy: {
  dist: {
    src: [
      '**',
      '!node_modules/**',
      '!Gruntfile.js',
      '!package.json'
    ],
    dest: 'dist/'
  }
}
```
