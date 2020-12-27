<head>
</head>
<body>
  <div id="globalArea" style="width:800px;height:420px"></div>
<script src="https://threejs.org/build/three.min.js"></script>    
<script src="https://raw.githack.com/syt123450/giojs/master/build/gio.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>

</body>
<script>
 
window.onload = function(){
var container = document.getElementById( "globalArea" );
// container.addEventListener("mousemove", updateDisplay, false);
let config = {
	"control": {
		"stats": false,
		"disableUnmentioned": true,
		"lightenMentioned": true,
		"inOnly": false,
		"outOnly": true,
		"initCountry": "JP",
		"halo": true,
		"transparentBackground": false,
		"autoRotation": false,
		"rotationRatio": 0
	},
	"color": {
		"surface": 1744048,
		"selected": 2141154,
		"in": 16777215,
		"out": 2141154,
		"halo": 2141154,
		"background": 0
	},
	"brightness": {
		"ocean": 0.5,
		"mentioned": 0.5,
		"related": 0.5
	}
};

let controller = new GIO.Controller( container, config );
controller.init();
let scene = controller.getScene();
// var universeMesh = new THREE.Mesh();

// create a universe background which is an Three.js object
// add universe to the scene
// let world = scene.loca .getWorldPosition();

//mesh = new THREE.Mesh(geo, mat);

// var matrix =THREE.rotating.matrixWorld;
// var abspos = THREE.matrix.multiplyVector3( Controller.center.clone() );
// var screenPos = screenXY(abspos);


// function screenXY(vec3){
//   var projector = new THREE.Projector();
//   var vector = projector.projectVector( vec3.clone(), Controller );
// 	var result = new Object();
// 	result.x = Math.round( vector.x * (window.innerWidth/2) ) + window.innerWidth/2;
// 	result.y = Math.round( (0-vector.y) * (window.innerHeight/2) ) + window.innerHeight/2;
// 	return result;
// }

// statsObject = controller.getStatsObject();

// defined a callback function, as a demo, this function simply output selectedCountry, relatedCountries which are passed parameters into console
// function callback ( selectedCountry, relatedCountries ) {

//         console.log(selectedCountry);
//         console.log(relatedCountries);

// }


function updateDisplay(){
  console.log(scene.rotation.x);
}


};
</script>