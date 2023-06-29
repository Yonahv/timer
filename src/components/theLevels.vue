<template>
  <h3>Rank</h3>
  <table>
    <tr>
        <th>Time</th>
        <th>Rank</th>
    </tr>
    <tr>
        <td>Under 250 ms</td>
        <td>Lightning reflexes!</td>
    </tr>
    
    <tr>
        <td>Under 400 ms</td>
        <td>Pretty fast!</td>
    </tr>
    
    <tr>
        <td>Over 400 ms</td>
        <td>Keep trying</td>
    </tr>
  
  </table>
</template>

<script>
export default {

}
</script>

<style>
    
table {
  border-collapse: collapse;
  width: 100%;
  max-width: 400px; 
  margin: 0 auto; 
}

th, td {
  padding: 8px;
  text-align: left;
}

th {
  background-color: #f2f2f2; 
}


table, th, td {
  border: 1px solid #ccc; 
}

table {
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1); 
}
</style>

