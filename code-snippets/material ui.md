# Material UI - Code Snippets

- [Official Documentation](https://material-ui.com/)

## Styling

### - Add CSS to a Component

```
import { makeStyles } from "@material-ui/core/styles";

const useStyles = makeStyles((theme) => ({
  root: {
    backgroundColor: "red",
    width: theme.spacing(10),
  },
}));

const MyComponent = () => {
  const classes = useStyles();
  return (
    <MaterialUiComponent className={classes.root}>
        Content
    </MaterialUiComponent>
  );
};

```

## Components

### - [Box](https://material-ui.com/components/box/#box)

- [Spacing Documentation](https://material-ui.com/system/spacing/)

```
import Box from "@material-ui/core/Box";
<Box mx='auto' my={-2} pt={3}>
  <Button />
</Box>
```

- [Flexbox Documentation](https://material-ui.com/system/flexbox/#flexbox)

```
import Box from "@material-ui/core/Box";
<Box display="flex">
  <Button />
</Box>
```

### - [Typografy](https://material-ui.com/components/typography/#typography)

```
import Typography from '@material-ui/core/Typography';<Typography variant="h1">
    Text
</Typography>
```

### - [Paper](https://material-ui.com/pt/api/paper/)

```
import Paper from '@material-ui/core/Paper';
<Paper variant="outlined" elevation={3} square>
    Content
</Paper>
```
