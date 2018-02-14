# React Native

## Expo

## Packages

### React Navigation

### React Native Typography
[Documentation](https://github.com/hectahertz/react-native-typography)
```
import { material } from 'react-native-typography'

<Text style={material.display1}>Hello Typography!</Text>
display1-4, headline, title, subheading, body2, body1, caption, button

import { systemWeights } from 'react-native-typography'
thin, light, regular, semibold, bold

import { iOSColors } from 'react-native-typography'
red, orange, yellow, green, blue, tealblue, purple, pink, white, customGray, lightGray, lightGray2, midGray, gray black
```

### React Native Elements

### React Video

### React Signature

### React Motion

### React Native Icons

### Styled Components
[Documentation](https://www.styled-components.com/docs/basics#react-native)

```
import styled from "styled-components";

const StyledView = styled.View`
  background-color: papayawhip;
`;

const StyledText = styled.Text`
  color: palevioletred;
`;

const Button = styled.button`
  /* Adapt the colours based on primary prop */
  background: ${props => props.primary ? 'palevioletred' : 'white'};
  color: ${props => props.primary ? 'white' : 'palevioletred'};

  font-size: 1em;
  margin: 1em;
  padding: 0.25em 1em;
  border: 2px solid palevioletred;
  border-radius: 3px;
`;
```