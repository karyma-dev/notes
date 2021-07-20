# Electron

## Table of Contents

-   [Creating Multiple Windows](creating-multiple-windows)
-   [Creating A Menu From Template](creating-a-menu-from-template)

### Creating Multiple Windows

```js
const createMainWindow = () => {
    mainWindow = new BrowserWindow({
        title: 'Main',
        width: 500,
        height: 600,
        icon: `${__dirname}/assets/icons/example.png`,
    })

    mainWindow.loadFile(`./app/index.html`)
}

const createAboutWindow = () => {
    aboutWindow = new BrowserWindow({
        title: 'About',
        width: 300,
        height: 300,
        icon: `${__dirname}/assets/icons/example.png`,
        resizable: false,
        backgroundColor: 'white',
    })

    aboutWindow.loadFile(`./app/about.html`)
}
```

### Creating A Menu From Template

```js
const menu = [
    ...(isMac
        ? [
              {
                  label: app.name,
                  submenu: [
                      {
                          label: 'About',
                          click: createAboutWindow,
                      },
                  ],
              },
          ]
        : [
              {
                  label: 'Help',
                  submenu: {
                      label: 'About',
                      click: createAboutWindow,
                  },
              },
          ]),
    {
        role: 'fileMenu',
    },
    ...(isDev
        ? [
              {
                  label: 'Developer',
                  submenu: [
                      { role: 'reload' },
                      { role: 'forcereload' },
                      { type: 'separator' },
                      { role: 'toggledevtools' },
                  ],
              },
          ]
        : []),
]

app.on('ready', () => {
    createMainWindow()

    const mainMenu = Menu.buildFromTemplate(menu)
    Menu.setApplicationMenu(mainMenu)
})
```
