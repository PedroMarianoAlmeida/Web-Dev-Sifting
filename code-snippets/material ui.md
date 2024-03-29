# Material UI - Code Snippets

- [Official Documentation](https://material-ui.com/)

- [Grid Tool](https://material-ui.com/components/grid/#interactive)

## Styling

### Add CSS to a Component

```javascript
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
    <MaterialUiComponent className={classes.root}>Content</MaterialUiComponent>
  );
};
```

## Components

### [Box](https://material-ui.com/components/box/#box)

- [Spacing Documentation (margins and paddings)](https://material-ui.com/system/spacing/)

```javascript
import Box from "@material-ui/core/Box";
import Button from '@material-ui/core/Button';

<Box mx="auto" my={-2} pt={3} boxShadow={5}>
  <Button>Button<Button />
</Box>;
```

- [Flexbox Documentation](https://material-ui.com/system/flexbox/#flexbox)

```javascript
import Box from "@material-ui/core/Box";
import Button from '@material-ui/core/Button';
import Typography from "@material-ui/core/Typography";

<Box display="flex" flexDirection="column" height="100%">
  <Button>Button<Button />
  <Box flexGrow={1} alignSelf="center">
      <Typography>Skills</Typography>
  </Box>
    <Typography>Social Network</Typography>
  </Box>
```

### [Typography](https://material-ui.com/components/typography/#typography)

```javascript
import Typography from "@material-ui/core/Typography";

<Typography variant="h1" align="center">
  Text
</Typography>;
```

### [Paper](https://material-ui.com/pt/api/paper/)

```javascript
import Paper from "@material-ui/core/Paper";

<Paper variant="outlined" elevation={3} square>
  Content
</Paper>;
```

### [Grid](https://material-ui.com/components/grid/)

- [Interactive Tool](https://material-ui.com/components/grid/#interactive)

```javascript
    import Grid from '@material-ui/core/Grid';
    import Typography from "@material-ui/core/Typography";
    import Button from '@material-ui/core/Button';

    <Grid container>
      <Grid item xs={12} sm={8}>
        <Typography paragraph>
          Lorem ipsum dolor sit amet, consectetur adipiscing elit
        </Typography>
      </Grid>

      <Grid xs={12} sm={4}>
        <Button>Button<Button />
      </Grid>
    </Grid>
```

### [IconButton](https://material-ui.com/components/buttons/#icon-buttons)

```javascript
import IconButton from "@material-ui/core/IconButton";
import DeleteIcon from "@material-ui/icons/Delete";

<IconButton aria-label="delete" disabled color="primary">
  <DeleteIcon />
</IconButton>;
```

### [Link](https://material-ui.com/components/links/)

```javascript
import Link from "@material-ui/core/Link";

<Link href="#" target="_blank" rel="noopener noreferrer" variant="body2">
  My Link
</Link>;
```

### [SnackBar (Toast)](https://material-ui.com/api/snackbar/)

```javascript
import { useState } from "react";

import IconButton from "@material-ui/core/IconButton";
import Snackbar from "@material-ui/core/Snackbar";
import DeleteIcon from "@material-ui/icons/Delete";

const EmailCopiedSnackbar = () => {
  const [open, setOpen] = useState(false);

  const handleClick = () => {
    navigator.clipboard.writeText("my text").then(() => setOpen(true));
  };

  return (
    <>
      <IconButton aria-label="email" color="primary" onClick={handleClick}>
        <DeleteIcon />
      </IconButton>

      <Snackbar
        anchorOrigin={{ vertical: "bottom", horizontal: "center" }}
        open={open}
        onClose={() => setOpen(false)}
        message="pedroalmeidaprogrammer@gmail.com was copied"
        autoHideDuration={1500}
      />
    </>
  );
};

export default EmailCopiedSnackbar;
```

### [Tooltip](https://material-ui.com/components/tooltips/)

```javascript
import Tooltip from "@material-ui/core/Tooltip";
import Button from "@material-ui/core/Button";

<Tooltip title="Add" placement="top-start">
  <Button>top-start</Button>
</Tooltip>;
```
