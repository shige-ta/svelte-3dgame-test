<script>
  import {
    Canvas,
    Scene,
    PerspectiveCamera,
    DirectionalLight,
    AmbientLight,
    BoxBufferGeometry,
    Mesh,
    MeshStandardMaterial,
    WebGLRenderer,
  } from "svelthree";

  let cubeGeometry = new BoxBufferGeometry(1, 1, 1);
  let cubeMaterial = new MeshStandardMaterial();

  let key;
	let keyCode;	

	let pos_list =[0.5, 0.6, 0];

	const handleKeydown = (e) => {
		key = e.key;
		keyCode = e.keyCode;


		if(key == "ArrowLeft")
		{
			pos_list[1] -= 0.1;
		}
		else if(key == "ArrowRight")
		{
			pos_list[1] += 0.1;
		}
		else if(key == "ArrowUp")
		{
			pos_list[0] -= 0.1;
		}
		else if(key == "ArrowDown")
		{
			pos_list[0] += 0.1;
		}
		console.log(key);
		console.log(keyCode);
	}
  </script>
 <svelte:window on:keydown={handleKeydown}/>

 <Canvas let:sti w={500} h={500}>

	<Scene {sti} let:scene id="scene1" props={{ background: 0xedf2f7 }}>
  
	  <PerspectiveCamera {scene} id="cam1" pos={[0, 0, 3]} lookAt={[0, 0, 0]} />
	  <AmbientLight {scene} intensity={1.25} />
	  <DirectionalLight {scene} pos={[3, 3, 3]} />
  
	  <Mesh
		{scene}
		geometry={cubeGeometry}
		material={cubeMaterial}
		mat={{ roughness: 0.5, metalness: 0.5, color: 0xff3e00 }}
		pos={[0, 0, 0]}
		rot={pos_list}
		scale={[1, 1, 1]} />
  
	</Scene>
  
	<WebGLRenderer
	  {sti}
	  sceneId="scene1"
	  camId="cam1"
	  config={{ antialias: true, alpha: true }} />
  
  </Canvas>
  {#if key == "ArrowLeft"}
<p>👈</p>
{:else if key == "ArrowRight"}
<p>🤜</p>
{:else if key == "ArrowUp"}
<p>👆</p>
{:else if key == "ArrowDown"}
<p>👇</p>
{:else}
<p>None</p>
{/if}
