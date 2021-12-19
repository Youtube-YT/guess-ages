<script>
    let age = "";
    let name = "";
    async function getAge() {
      fetch('https://api.agify.io/?name=' + age)
        .then((response) => response.json())
        .then((data) => {
          //Able to change whatever name you like Example: weatherTemparature = data.temperature the name of data should not be changed.
           age = data.age; // Path for temperature
          name = data.name; // Path for description
        });
    }
        </script>
        <p>Ages: {age}</p>