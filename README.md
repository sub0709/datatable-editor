# datatable-editor

![](https://github.com/sub0709/datatable-editor/blob/master/sample.png)

## basic usage

```js
var table1 = $('#table1').DataTable();
datatableEdit({
  dataTable : table1,
  columnDefs : [
    {
      targets : 0
    }
  ]
});
```

## multiple

```js
var tables = $('.table').DataTable();
datatableEdit({
  dataTable : tables,
  columnDefs : [
    {
      targets : 0
    }
  ]
});
```

## onEdited event

```js
datatableEdit({
  dataTable : table1,
  columnDefs : [
    {
      targets : 0
    },

    {
      targets : 2
    },
    {
      onEdited : function(prev, changed, index, cell) {
        console.log(prev, changed, index, cell);
      },
      targets : 3
    },
  ]
});
```

```js
datatableEdit({
  dataTable : table1,
  columnDefs : [
    {
      targets : 0
    },

    {
      targets : 2
    },
    {
      onEdited : function(prev, changed, index, cell) {
        console.log('each cell');
        console.log(prev, changed, index, cell);
      },
      targets : 3
    },
  ],
  onEdited : function(prev, changed, index, cell) {
    console.log('every cell');
    console.log(prev, changed, index, cell.row(index.row).data());
  }

});
```
