# listifyJSON
Client side vanilla JS that generates a collapsible list from JSON, which can be sorted by keys

    <!-- include source file -->
    <script src="listifyJSON.js"></script>
    
    <script>
    // json object
    var data = {'some': 'object', 'can': {'be': 'nested'}} 
    
    // specify the initial sort key (user then selects sort key from list after list is generated)
    var default_sortKey = 'name'  
    
    // Generate a list of sort keys and append the list to a parent container
    document.getElementById('main').appendChild(listifySortKeys(jsonData, default_sortKey));  
    
    // add some spacers if desired
    var hr = document.createElement('HR'); 
    var br1 = document.createElement('BR');
    var br2 = document.createElement('BR');
    var br3 = document.createElement('BR');
    document.getElementById('main').appendChild(br1);
    document.getElementById('main').appendChild(br2);
    document.getElementById('main').appendChild(hr);
    document.getElementById('main').appendChild(br3);
    
    // pass json to sort method (Only required if specifying a default sort key)
    var sortedObject = sortObject(jsonData, default_sortKey);
    
    // Generate listified JSON and append to parent container
    document.getElementById('main').appendChild(generateListifiedJSON(sortedObject, default_sortKey));
    </script>
