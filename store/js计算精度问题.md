    <script>
      //  浮点数的精确计算 相加
      function floatAdd(a, b) {
        let c = '';
        let d = '';
        let e = '';
        try {
          c = a.toString().split('.')[1].length;
        } catch (f) {
          c = 0;
        }
        try {
          d = b.toString().split('.')[1].length;
        } catch (f) {
          d = 0;
        }
        e = Math.pow(10, Math.max(c, d));
        return (transformMul(a, e) + transformMul(b, e)) / e;
      }
  
      function transformMul(a, b) {
        let c = 0;
        const d = a.toString();
        const e = b.toString();
        try {
          c += d.split('.')[1].length;
          c += e.split('.')[1].length;
        } finally {
          return Number(d.replace('.', '')) * Number(e.replace('.', '')) / Math.pow(10, c);
        }
      }
  
      Number.prototype.add = function (arg) {
          return floatAdd(arg, this);
      }
  
      var t1 = 0.01,t2=0.01;
      console.log(Number(t1).add(Number(t2)));
      document.getElementById('id1').onchange=function(){
        document.getElementById('id3').value = Number(document.getElementById('id1').value).add(Number(document.getElementById('id2').value))
      }
      document.getElementById('id2').onchange=function(){
        document.getElementById('id3').value = Number(document.getElementById('id1').value).add(Number(document.getElementById('id2').value))
      }
    </script>
