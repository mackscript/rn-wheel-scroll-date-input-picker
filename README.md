# rn-wheel-scroll-date-input-picker

A simple and customizable scrollable date picker for React Native, allowing users to input or select dates with a custom text field.

## Installation

To install the package, run:

```bash
npm install rn-wheel-scroll-date-input-picker
```

Or using Yarn:

```bash
yarn add rn-wheel-scroll-date-input-picker
```

## Usage

Here's how you can use rn-wheel-scroll-date-input-picker in your project:

```bash
import React, { useState } from 'react';
import { View, Text, Button } from 'react-native';
import RnDateInputPicker from 'rn-wheel-scroll-date-input-picker';

const App = () => {
   const [showDateModal, setShowDateModal] = useState(false);
   const [newdate, setNewDate] = useState(new Date());
   const closeModal = () => {
    setShowDateModal(false);
   };

  const onSelected = values => {
    setNewDate(values.date);
  };

  return (
    <View>
      <Button title="Select Date" onPress={() => setShowDateModal(true)} />
       <RnDateInputPicker
        lastYear="1900"
        defaultDate={newdate} // 2024-09-09T11:33:40.097Z
        visible={showDateModal} // show Modal
        closeModal={closeModal} // close Modal
        onSelected={onSelected} // seleted Date
      />
    </View>
  );
};

export default App;
```

## Props

| Prop Name     | Type       | Default      | Description                                                                                                       |
| ------------- | ---------- | ------------ | ----------------------------------------------------------------------------------------------------------------- |
| `lastYear`    | `string`   | `"1900"`     | The minimum year limit that can be selected in the date picker.                                                   |
| `defaultDate` | `Date`     | `new Date()` | The default date that will be selected when the date picker opens. Pass a JavaScript `Date` object.               |
| `visible`     | `boolean`  | `false`      | Controls the visibility of the date picker modal. Set `true` to show the modal, and `false` to hide it.           |
| `closeModal`  | `function` | `null`       | Callback function that closes the modal. Typically passed as a function to hide the modal.                        |
| `onSelected`  | `function` | `null`       | Callback function triggered when a date is selected. The selected date is passed as a parameter to this function. |
