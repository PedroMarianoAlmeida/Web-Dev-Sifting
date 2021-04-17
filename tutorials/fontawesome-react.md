# Using Fontwesome in React projects

- [Oficial Documentation](https://fontawesome.com/how-to-use/on-the-web/using-with/react)

### Step 1: Download packages

- Essencial:

```
npm i --save @fortawesome/fontawesome-svg-core
npm install --save @fortawesome/react-fontawesome
```

- Actual icons (choose the package(s) that contains the icons that you want use)

```
npm install --save @fortawesome/free-solid-svg-icons
npm install --save @fortawesome/free-regular-svg-icons
npm install --save @fortawesome/free-brands-svg-icons
```

### Step 2: Choose the icon that you will use

- Choose a icon here: [Free Icons](https://fontawesome.com/icons?d=gallery&p=2&s=brands,regular,solid&m=free)

- After the choosing, remember this data: The name of the icon and its style, see in the example

![image](https://github.com/PedroMarianoAlmeida/Web-Dev-Panning/blob/master/images/tutorial-fontawesome-react-1.PNG)

### Step 2: Include icon component in your code

- Import the necessary components

```
import { FontAwesomeIcon } from '@fortawesome/react-fontawesome'
import { faCoffee } from '@fortawesome/free-solid-svg-icons'
```

      Note 1: The name of Icon will be in camelCase
   
      Note 2: Check if you are trying to get from the correct importation @fontawsome (because there are 3)

- Put the icon where you want:

```
<FontAwesomeIcon icon={faCoffee} />
```

### Step 3: Choose the size

```
<FontAwesomeIcon icon={faCoffee} size="lg"/>
```

Possible values: xs, sm, lg, 2x, 3x, 5x, 7x, 10x
