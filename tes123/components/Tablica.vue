<template>
  <div class="container">
            <div class="tab tab-1">
                <table id="table" border="1">
                    <tr>
                        <th>Title</th>
                        <th>State</th>
                        <th>Area</th>
                        <th>Rooms</th>
                        <th>Lift</th>
                        <th>Address</th>
                        <th>Rentalgross</th>
                    </tr>
                    <tr v-for="apartment in apartments" :key="apartment.id">

                        <td>{{apartment.title}}</td>
                        <td>{{apartment.state}}</td>
                        <td>{{apartment.area}}</td>
                        <td>{{apartment.rooms}}</td>
                        <td>{{apartment.lift}}</td>
                        <td>{{apartment.address}}</td>
                        <td>{{apartment.rentalgross}}</td>
                    </tr>
                </table>
            </div>
            <div class="tab tab-2">
                Title :<input type="text" name="fname" id="fname">
                State :<input type="text" name="lname" id="lname">
                Area :<input type="number" name="area" id="area">
                Rooms :<input type="number" step="0.01" name="rooms" id="rooms">
                Lift :<input type="checkbox" name="lift" id="lift">
                Address :<input type="string" name="address" id="address">
                Rentalgross :<input type="number" name="rentalgross" id="rentalgross">
                <button onclick="addHtmlTableRow();">Add</button>
                <button onclick="editHtmlTbleSelectedRow();">Edit</button>
                <button onclick="removeSelectedRow();">Remove</button>
            </div>
        </div>
</template>
<script>
export default {
  props: {
    apartments: {
      type: Object
    }
  }
}
</script>
