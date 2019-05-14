# react-tablegen
A react component that accepts data, allows you to select which information from the data to be printed on the table, gives the user the ability to sort the data, and allows the developer to pass in custom components for the table foot and head.

## Installation
```shell
npm i react-tablegen
```

## Example

```js
import React from 'react'
import Table from 'react-tablegen'

class App extends React.Component {

    render() {
        const data = [
            {
                first_name: "Abdul",
                last_name: "Amoud"
            },
            {
                first_name: "John",
                last_name: "Doe"
            },
            {
                first_name: "Haowei",
                last_name: "Zheng"
            }
        ]

        const header = () => (
            <tr>
                <th colSpan="2">
                    This is our names table
                </th>
            </tr>
        )

        const tfoot = () => (
            <tfoot>
                <tr>
                    <th colSpan="2">
                        This is our tables foot
                    </th>
                </tr>
            </tfoot>
        )

        return ( 
        	<React.Fragment >
                <Table
                    data={data}
                    columnHeaders={['First Name', 'Last Name']}
                    columnKeys={['first_name', 'last_name']}
                    additionalHeader={header}
                    foot={tfoot}
                />
          	</React.Fragment>
        )
    }
}
export default App
```

## Props
* `data`: `required` `array`, data that will be populated on each row of the table.
* `columnHeaders`: `required` `array`, an array of the values that will be populated in the table header columns.
* `columnKeys`: `required` `array`, an array of the keys in the data dictonaries that correspond with the order of the `columnHeaders` array.
* `additionalHeader`: `func`, a function that returns an element that will be printed above the table header.
* `tfoot`: `func`, a function that returns an element that will be printed under the `<tbody>` element.

