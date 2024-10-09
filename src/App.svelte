<script>
	// You can define any props or reactive variables you might need here
  </script>
  
  <main>
	<h1>Welcome to Dance Master!</h1>
	<p>Explore various features to enhance your dance skills.</p>
	
	<div class="menu">
	  <a href="/freestyle" class="menu-item">Freestyle</a>
	  <a href="/upload-choreo" class="menu-item">Upload Choreo</a>
	  <a href="/progress" class="menu-item">Track Progress</a>
	</div>
	
	<p>Get started with your dance journey!</p>
  </main>
  
  <style>
	main {
	  text-align: center;
	  padding: 1em;
	  max-width: 800px; 
	  margin: 0 auto;
	}
  
	h1 {
	  color: #ff3e00; 
	  text-transform: uppercase;
	  font-size: 3em; 
	  font-weight: bold; 
	}
  
	p {
	  font-size: 1.2em; 
	}
  
	.menu {
	  display: flex;
	  justify-content: center; 
	  gap: 20px; 
	  margin: 20px 0; 
	}
  
	.menu-item {
	  text-decoration: none; 
	  background-color: #ff3e00; 
	  color: white; 
	  padding: 10px 20px; 
	  border-radius: 5px; 
	  transition: background-color 0.3s; 
	}
  
	.menu-item:hover {
	  background-color: #e03e00; 
	}
  
	@media (min-width: 640px) {
	  main {
		max-width: none; 
	  }
	}
  </style>
  