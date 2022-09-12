# 操作element里面的from表单的数据时视图不刷新

## 1.使用this.$nextTick() 和this.$forceUpdate();强制刷新页面

```javascript
handleShowPhone(index,row){

    this.$nextTick(() => {
 
    this.tableData[index].isShow = true;
 
    this.$forceUpdate();
 ```

 