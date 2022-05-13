# React Dialog

Show Dialogs with easy way in react JS, super easy to use and can handel all the major user cases.
##### Based on the React hooks and reactive programing.
#### No extra dependencies pure react js code & lightweight.

## Features
1. useDialog Hook to show dialogs in functional components.
3. use dialog from any UI library i.e MUI/bootstrap  or any other UI library
2. Open source Free to use.

## Installation
```sh
npm install @surinderlohat/react-dialog
or
yarn add @surinderlohat/react-dialog
```
## How to use
- Add Dialog Provider
App.tsx
```sh
import { FC } from 'react';
import { DialogProvider } from '@surinderlohat/react-dialog';
import BootstrapDialog from './BootstrapDialog';
import MUIDialog from './MUIDialog';

// App.tsx
const App: FC = () => {
  return (
    <DialogProvider>
      <BootstrapDialog />
      <MUIDialog />
    </DialogProvider>
  );
};

export default App;
```
- Import Use Dialog Hook that's it 
  #### MUI Dialog Example :
```sh
import { FC } from 'react';
import { Box, Button, Dialog, DialogTitle } from '@mui/material';
import { useDialog } from '@surinderlohat/react-dialog';

const MuiDialog: FC = () => {
  const dialog = useDialog();

  // Show MUI Dialog
  const showMuiDialog = () => {
    dialog.openDialog(
      <Dialog open={true} onClose={() => dialog.closeDialog()}>
        <DialogTitle>MUI Dialog Example</DialogTitle>
        <p>Welcome to react dialog</p>
      </Dialog>
    );
  };

  return (
    <Box sx={{ display: 'flex', justifyContent: 'center' }}>
      <Button onClick={showMuiDialog}>SHOW MUI DIALOG </Button>
    </Box>
  );
};
export default MuiDialog;
```
 #### Bootstrap Dialog Example :
```sh
import { FC } from 'react';
import { useDialog } from '@surinderlohat/react-dialog';
import { Modal, Button } from 'react-bootstrap';
import 'bootstrap/dist/css/bootstrap.min.css';

const BootstrapDialog: FC = () => {
  const dialog = useDialog();

  // Show Bootstrap Dialog
  const showBootstrapDialog = () => {
    dialog.openDialog(
      <Modal.Dialog>
        <Modal.Header closeButton>
          <Modal.Title>Bootstrap Dialog Example</Modal.Title>
        </Modal.Header>
        <Modal.Body>
          <p>Modal body text goes here.</p>
        </Modal.Body>
        <Modal.Footer>
          <Button variant="secondary" onClick={() => dialog.closeDialog()}>
            Close
          </Button>
          <Button variant="primary">Save changes</Button>
        </Modal.Footer>
      </Modal.Dialog>
    );
  };

  return (
    <div>
      <Button onClick={showBootstrapDialog}>Show Dialog</Button>
    </div>
  );
};

export default BootstrapDialog;
```
## License
MIT **Free Software!**
