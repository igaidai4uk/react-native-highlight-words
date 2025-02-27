# RN Highlight Words

React Native component used to highlight words within a larger body of text. This is a port of [react-highlight-words](https://github.com/bvaughn/react-highlight-words).

## Changelog

-   [x] OnPress event added for Normal/Highlighted text

## Installation

Using [npm](https://www.npmjs.com/package/rn-highlight-words):

```
npm i --save react-native-highlight-words
```

## Usage

To use it, just provide it with an array of search terms and a body of text to highlight:

```jsx
import Highlighter from "rn-highlight-words";

<Highlighter
    highlightStyle={{ backgroundColor: "yellow" }}
    searchWords={["and", "or", "the"]}
    textToHighlight="The dog is chasing the cat. Or perhaps they are just playing?"
    onPressNormalText={() => console.log("normal text is clickeddd!")}
    onPressHighlightedText={() => console.log("highlighted text is clickeddd!")}
/>;
```

And the `Highlighter` component will highlight all occurrences of search terms within the text:

<img src="https://github.com/adityasonel/rn-highlight-words/blob/master/sample.gif">

And if you want to get highlighted text that clicked, get in `onPressHighlightedText` as

```
onPressHighlightedText = {text => console.log("highlighted text that click: " + text)}
```

## Props

| Property               | Type          | Required? | Description                                                                                                             |
| :--------------------- | :------------ | :-------: | :---------------------------------------------------------------------------------------------------------------------- |
| autoEscape             | Boolean       |           | Escape characters which are meaningful in regular expressions                                                           |
| highlightStyle         | Object        |           | Styles applied to highlighted text                                                                                      |
| sanitize               | Function      |           | Process each search word and text to highlight before comparing (eg remove accents); signature `(text: string): string` |
| searchWords            | Array<String> |     ✓     | Array of search words                                                                                                   |
| style                  | Object        |           | Styles applied to the text wrapper                                                                                      |
| textToHighlight        | String        |     ✓     | Text to highlight matches in                                                                                            |
| onPressNormalText      | Function      |           | onPress event for normal text                                                                                           |
| onPressHighlightedText | Function      |           | onPress event for highlighted text (returns text that clicked)                                                          |

## License

[MIT License](LICENSE)
