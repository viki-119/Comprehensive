    <script type="text/javascript">
      Array.prototype.afterArray=function(){
        console.log('this=',this);
       this.splice(0,1);
      };
      arr=[1,1,1,5,1,1,1,6];
      for (var i=0;i<arr.length;i++) {
        console.log('前arr=',arr);
        console.log('i=',i);
        console.log('arr.length=',arr.length);
        console.log('arr[i]=',arr[i]);
        if (arr[i] === 1) {
           arr.afterArray();
        }
        console.log('后arr=',arr);
      }
    </script>
