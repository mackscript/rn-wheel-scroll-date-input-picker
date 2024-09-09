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
