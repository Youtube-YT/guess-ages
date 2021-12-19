<script>
    let age = "";
    let name = "";
    async function getAge() {
      fetch('https://api.agify.io/?name=' + name)
        .then((response) => response.json())
        .then((data) => {
          //Able to change whatever name you like Example: weatherTemparature = data.temperature the name of data should not be changed.
          name = data.name; // Path for name
          age = data.age; // Path for age
        });
    }
        </script>
        <h1>Guess Your Age 🤔</h1>

        <form on:submit|preventDefault={getAge}>    
            <label for="location">Name:</label>
            <input id="location" bind:value={name} type="text" />
            <button type="submit">Check</button>
        </form>
        <p>Ages: {age}</p>