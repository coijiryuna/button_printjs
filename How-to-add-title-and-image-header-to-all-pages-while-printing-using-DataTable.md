## Step 1
Download below JS file and replace your print.button.js with below it,
https://github.com/aravindnc/Buttons/blob/repeating-print-head/js/buttons.print.js

## Step 2
Add new option **repeatingHead** inside the button settings. 

Below are the options for repeatingHead,
```javascript
{
    logo: 'Your logo URL to be repeated',
    logoPosition: 'right', // left, center, right
    logoStyle: '', // any css eg: padding:10px;
    title: '<h3>Sample Heading</h3>' // your heading
}
```

A sample is given below. 
```javascript
<script>
    $(document).ready(function() {
        // DataTable initialisation
        $('#example').DataTable({
            "dom": 'Bfrtip',
            "paging": true,
            "autoWidth": true,
            "columnDefs": [{
                "visible": true,
                "targets": -1
            }],
            buttons: [{
                extend: 'print',
                autoPrint: true,
                title: '',

                //For repeating heading.
                repeatingHead: {
                    logo: 'https://www.google.co.in/logos/doodles/2018/world-cup-2018-day-22-5384495837478912-s.png',
                    logoPosition: 'right',
                    logoStyle: '',
                    title: '<h3>Sample Heading</h3>'
                }
            }]
        });
    });
</script>
```

## Step 3

If you want to remove the borders around logo, add a new class **dt-print-table** to your table and add below style to your css file.
```css
@media print
{
html, body { height: auto; }
.dt-print-table, .dt-print-table thead, .dt-print-table th, .dt-print-table tr {border: 0 none !important;}
}
```

Thats all :)