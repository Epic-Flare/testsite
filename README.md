# testsite

<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Scoreboard</title>
<script src="https://cdn.tailwindcss.com"></script>
<style>
  /* Additional styles if needed */
</style>
</head>
<body class="bg-white text-gray-800">

<div class="min-h-screen flex items-center justify-center">
  <div class="bg-gray-100 p-8 rounded-lg shadow-lg max-w-md w-full">
    <h1 class="text-xl font-bold mb-4">Topic: "What do you think of the AAA bill?"</h1>
    <div class="mb-4">
      <label for="necessity" class="block text-sm font-medium text-gray-700">Necessity</label>
      <input type="range" id="necessity" name="necessity" min="0" max="10" class="w-full h-2 bg-gray-200 rounded-lg appearance-none cursor-pointer">
      <span id="necessityValue" class="text-sm font-medium text-gray-700"></span>
    </div>
    <div class="mb-4">
      <label for="suitability" class="block text-sm font-medium text-gray-700">Suitability</label>
      <input type="range" id="suitability" name="suitability" min="0" max="10" class="w-full h-2 bg-gray-200 rounded-lg appearance-none cursor-pointer">
      <span id="suitabilityValue" class="text-sm font-medium text-gray-700"></span>
    </div>
    <div class="flex justify-end">
      <button id="submit" class="px-4 py-2 bg-green-500 text-white font-bold rounded hover:bg-green-600 focus:outline-none focus:ring-2 focus:ring-green-300">Submit</button>
    </div>
  </div>
</div>

<script>
  // JavaScript logic for handling the form submission and displaying the slider values
  const necessitySlider = document.getElementById('necessity');
  const suitabilitySlider = document.getElementById('suitability');
  const necessityValueDisplay = document.getElementById('necessityValue');
  const suitabilityValueDisplay = document.getElementById('suitabilityValue');

  necessitySlider.addEventListener('input', function() {
    necessityValueDisplay.textContent = `Value: ${necessitySlider.value}`;
  });

  suitabilitySlider.addEventListener('input', function() {
    suitabilityValueDisplay.textContent = `Value: ${suitabilitySlider.value}`;
  });

  document.getElementById('submit').addEventListener('click', function() {
    const necessityValue = necessitySlider.value;
    const suitabilityValue = suitabilitySlider.value;
    
    // Placeholder for user authentication check
    const userIsLoggedIn = true; // This should be replaced with actual authentication logic
    
    if (userIsLoggedIn) {
      // Logic to store the result in the database and redirect to the 'Results Page'
      console.log('Necessity:', necessityValue, 'Suitability:', suitabilityValue);
      // Redirect to Results Page (placeholder)
      window.location.href = 'ResultsPage.html';
    } else {
      // Redirect to Login Page
      window.location.href = 'LoginPage.html';
    }
  });

  // Initialize the value display
  necessityValueDisplay.textContent = `Value: ${necessitySlider.value}`;
  suitabilityValueDisplay.textContent = `Value: ${suitabilitySlider.value}`;
</script>

</body>
</html>
