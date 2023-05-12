# JSZoomInHoverEffectsImage

```CSS
/* BRGIN CLASS */
/*parent*/
.hp-parent-thunbnail {
    
  overflow: hidden;
  position: relative;
  float: left;
  display: inline-block;
  cursor: pointer;

}

/*child*/
.hp-firstChild-thunbnail,
.hp-firstChild-thunbnail {
 
  background-size: cover;
  background-repeat: no-repeat;
  -webkit-transition: all .5s;
  -moz-transition: all .5s;
  -o-transition: all .5s;
  transition: all .5s;
	
}

/*parent*/                   /*child*/  
.hp-parent-thunbnail:hover .hp-firstChild-thunbnail, 
.hp-parent-thunbnail:focus .hp-firstChild-thunbnail{
  -ms-transform: scale(1.2);
  -moz-transform: scale(1.2);
  -webkit-transform: scale(1.2);
  -o-transform: scale(1.2);
  transform: scale(1.2);
}

/*parent*/                   /*child*/
.hp-parent-thunbnail:hover .hp-firstChild-thunbnail:before, 
.hp-parent-thunbnail:focus .hp-firstChild-thunbnail:before {
  display: block;
}

/*parent*/
.hp-parent-thunbnail:before {
  content: "";
  display: none;
  position: absolute;
  top: 0;
  left: 0;

}

/* parent container */
.hp-container-thunbnail:hover {

 -webkit-box-shadow: 0 5px 10px 0px #9e9e9e5c;
  box-shadow: 0 5px 10px 0px #9e9e9e5c;
}

/* END CLASS */
```

```JS
(function() {
	
 const HPThumbnail = {
    
    p : null, 
    c : null,
	b : null,
	q : null,
	 
    HPAction : function() {
    
      let elemParent    = this.p?? null;
      let elemChildren  = this.c?? null;
      let elemContainer = this.b?? null;
    
      let cParentID    = this.__qs(elemParent); 
      let cChildrenID  = this.__qs(elemChildren); 
      let cContainerID = this.__qs(elemContainer); 
	   
      const ___Only = function(e) { return document.querySelector(e); }
	   
      const HPFocus = function() { 
		 
	     if(this.q !== null) { 
		   
		     HPHover(cParentID, 'hp-parent-thunbnail');	 
		     HPHover(cChildrenID, 'hp-firstChild-thunbnail');	
		     HPHover(cContainerID, 'hp-container-thunbnail');		 
		 
		   }			 
     }
	   
     const HPHover = function( et = [] , se ) { 
         
		     et.forEach(function( v ) {
			   
		       let tID = '#' +v.id;
		       let activeID = ___Only(tID)
		       activeID.classList.add(se);
				  				 			
		     });  		   
     }	  
	   
     return {
		   
        Focus : HPFocus()
 
     }
	   
  },
  __qs : function( e ) {
	  
	  if(this.q !== null) { return document.querySelectorAll( e );   } 
	  return document.querySelector( e );  
	  
  }	 
	 
 }	
	
 /* Latest Right Column */ 
 // Main container where the dropshadows appear 
 HPThumbnail.b = '.hp-latest-col-right-container';
 // Parent elem where the child image bg was insalled
 HPThumbnail.p = '.hp-latest-col-right-parent';
 // Child where the bg image insalled
 HPThumbnail.c = '.hp-latest-col-right-child';
 // Anything as to be return querySelectAll() just not null!
 HPThumbnail.q = 'selectAll';		
 HPThumbnail.HPAction();
	
})();
```
