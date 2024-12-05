# react-native-speedometer [![Build Status] [![npm version](https://badge.fury.io/js/react-native-speedometer.svg)](https://badge.fury.io/js/react-native-speedometer) [![npm downloads](https://img.shields.io/npm/dt/react-native-speedometer.svg)](https://npm-stat.com/charts.html?package=react-native-speedometer&from=2018-02-17&to=2018-12-28) <img src="https://img.shields.io/badge/module%20formats-umd%2C%20cjs%2C%20esm-green.svg" alt="module formats: umd, cjs, esm"></a>


A Customizable Speedometer Implementation in React Native

### Installation

```bash
$ npm i react-native-speedometer --save
```

### Basic Usage
```
import React, { Component } from 'react';
import {
  SafeAreaView,
  StyleSheet,
  TextInput
} from 'react-native';

import RNSpeedometer from 'react-native-speedometer'

class App extends Component {
  state = {
    value: 0,
  };

  onChange = (value) => this.setState({ value: parseInt(value) });

  render() {
     return (
        <SafeAreaView style={style.container}>
          <TextInput placeholder="Speedometer Value" style={styles.textInput} onChangeText={this.onChange} />
          <RNSpeedometer value={this.state.value} size={200}/>
        </SafeAreaView>
      );
  }
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
  },
  textInput: {
    borderBottomWidth: 0.3,
    borderBottomColor: 'black',
    height: 25,
    fontSize: 16,
    marginVertical: 50,
    marginHorizontal: 20,
  },
});
```

### Properties
| Prop  | Default  | Type | Description |
| :------------ |---------------:| :---------------| :-----|
| value | required | number | Current Value |
| size | [Default Labels](#defaults) | number | Size |
| defaultValue | 50 | number | Default Value |
| minValue | 0 | number | Minimum Limit |
| maxValue | 100 | number | Maximum Value |
| allowedDecimals | 0 | number | Allowed Decimal Places |

### Defaults
```
  size: deviceWidth - 20,
  defaultValue: 50,
  minValue: 0,
  maxValue: 100,
  easeDuration: 500,
  labels: [
    {
      name: 'Too Slow',
      labelColor: '#ff2900',
      activeBarColor: '#ff2900',
    },
    {
      name: 'Very Slow',
      labelColor: '#ff5400',
      activeBarColor: '#ff5400',
    },
    {
      name: 'Slow',
      labelColor: '#f4ab44',
      activeBarColor: '#f4ab44',
    },
    {
      name: 'Normal',
      labelColor: '#f2cf1f',
      activeBarColor: '#f2cf1f',
    },
    {
      name: 'Fast',
      labelColor: '#14eb6e',
      activeBarColor: '#14eb6e',
    },
    {
      name: 'Unbelievably Fast',
      labelColor: '#00ff6b',
      activeBarColor: '#00ff6b',
    },
  ],
  needleImage: require('./images/speedometer-needle.png'),
  wrapperStyle: {},
  outerCircleStyle: {},
  halfCircleStyle: {},
  imageWrapperStyle: {},
  imageStyle: {},
  innerCircleStyle: {},
  labelWrapperStyle: {},
  labelStyle: {},
  labelNoteStyle: {},
```
