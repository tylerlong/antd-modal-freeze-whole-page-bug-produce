# Ant Design Modal freeze whole page bug reproduce demo

## Online demo

https://chuntaoliu.com/antd-modal-freeze-whole-page-bug-produce/

## How to run

```
yarn serve
```

Go to http://localhost:1234

- Click the button once to open the modal.
- Close the modal
- Click the button again

You will find that the whole page is frozon and you cannot click anything any more.

## Update

It is caused by:

```css
body > div {
  position: fixed;
  top: 0;
  left: 0;
  height: 100vh;
  width: 100vw;
}
```

The first time you open a modal, Ant Design will insert a `<div/>` under `<body/>`

## Workaround

Change the css to

```css
div#react-root {
  position: fixed;
  top: 0;
  left: 0;
  height: 100vh;
  width: 100vw;
}
```
