# @emotion/native

> Style and render React Native components using emotion

## Install

```
npm install @emotion/native
```

or if you use yarn

```
yarn add @emotion/native
```

This package also depends on `react`, `react-native` and `prop-types` so make sure you've them installed.

## Example

```js
import React from 'react'
import { AppRegistry } from 'react-native';
import styled, { css } from '@emotion/native'

const Container = styled.View`
  display: flex;
  justify-content: center;
  align-items: center;
  margin: 50px;
`

const Description = styled.Text({
  color: 'hotpink'
})

const Image = styled.Image`
  padding: 40px;
`

const emotionLogo =
  'https://cdn.rawgit.com/emotion-js/emotion/master/emotion.png'

class App extends React.Component {
  render() {
    return (
      <Container
        style={css`
          border-radius: 10px;
        `}
      >
        <Description style={{ fontSize: 45, fontWeight: 'bold' }}>
          Emotion Primitives
        </Description>
        <Image
          source={{
            uri: emotionLogo,
            height: 150,
            width: 150
          }}
        />
      </Container>
    )
  }
}

AppRegistry.registerComponent('ExampleApp', () => App);
```

## Theming

Use `emotion-theming` for theming support.

```js
import React from 'react'
import styled, { css } from '@emotion/native'

import { ThemeProvider } from 'emotion-theming'

const theme = {
  color: 'hotpink',
  backgroundColor: 'purple'
}

const Container = styled.View`
  display: flex;
  justify-content: center;
  align-items: center;
  margin: 50px;
  border: 5px solid red;
  background-color: ${props => props.theme.backgroundColor};
`

const Description = styled.Text({
  color: 'hotpink'
})

const Image = styled.Image`
  padding: 40px;
`

const emotionLogo =
  'https://cdn.rawgit.com/emotion-js/emotion/master/emotion.png'

class App extends React.Component {
  render() {
    return (
      <ThemeProvider theme={theme}>
        <Container
          style={css`
            border-radius: 10px;
          `}
        >
          <Description style={{ fontSize: 45, fontWeight: 'bold' }}>
            Emotion Primitives
          </Description>
          <Image
            source={{
              uri: emotionLogo,
              height: 150,
              width: 150
            }}
          />
        </Container>
      </ThemeProvider>
    )
  }
}
```