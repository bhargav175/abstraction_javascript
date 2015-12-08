# abstraction_javascript
Private, Private static and Public static variables

    //Closure returning IIFE
    var Car = (function(){
       
      //private static variable
      var privateCount = 0;
      
      return function Car(){
        privateCount++;
        Car.count++;
        Car.getPrivateCount = () => privateCount;
        
        //private variable
        var id = Math.random();
        
        this.getId = function(){
            console.log(id); 
        }
      }
    })();
    
    
    //public static variable
    Car.count = 0;
  
  
    var c1 = new Car();
    var c2 = new Car(); 
  
    console.log(c1.getId(),c2.getId(), Car.getPrivateCount(),Car.count); //some number,some number, 2,2
