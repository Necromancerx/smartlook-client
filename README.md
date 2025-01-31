# Smartlook-client

Imports and initializes Smartlook recorder into a page.

1.  Installation
    ```
    npm install smartlook-client --save
    ```
    or
    ```
    yarn add smartlook-client
    ```
2.  Import
    ```
    import smartlookClient from 'smartlook-client'
    ```
    or
    ```
    var smartlookClient = require('smartlook-client')
    ```
3.  API
    ```
    init(string key)
    ```
    ```
    track(string eventName, object<key:value> props)
    ```
    ```
    identify(integer | string userId, object<key:value> props)
    ```
    ```
    anonymize()
    ```
    ```
    disable()
    ```
    ```
    consentForms(string | false consent)
    ```
    ```
    consentIP(string | false consent)
    ```
    ```
    consentAPI(string | false consent)
    ```
    ```
    getData(function callback)
    ```
    ```
    restart()
    ```
    ```
    error(string | Error error)
    ```
4.  Example usage in React

    Usage in other libraries is similar.

    ```
    import React, { Component } from 'react'
    import smartlookClient from 'smartlook-client'

    class App extends Component {
      handleIdentify = () => {
        smartlookClient.identify(12345, {
         name: 'John Doe',
         email: 'email@domain.com',
         // other custom properties
       })
      }
      handleTrack = () => {
       smartlookClient.track('transaction', {
         "value": 150,
         "currency": "usd",
         "product": "Product Description",
         // other custom properties
       });
      }
     handleDisable = () => {
       smartlookClient.disable()
     }
      render() {
        return (
          <div>
            <button onClick={this.handleIdentify}>Identify visitor</button>
           <button onClick={this.handleTrack}>Track event</button>
            <button onClick={this.handleDisable}>Disable recording</button>
          </div>
        )
      }
      componentDidMount() {
        smartlookClient.init('43bc84d9a8406exxxxxxxxxb5601f5bbf8d2ed')
      }
    }

    export default App
    ```

For more info visit https://www.smartlook.com/docs/api.html
