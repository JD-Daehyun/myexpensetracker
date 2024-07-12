# Expense Tracker Website

This project is an expense tracker website built using React, Chakra UI, and Global Context State management.

## Features

### Global Context State Management 
Global Context State management allows you to manage and share state across multiple components without prop drilling.

#### Creating Global Context
- **`createContext`**: Define the context and provider to share state globally.
- **`useContext`**: Use the context in components to access and update the global state.


### Chakra UI
Chakra UI is a simple, modular, and accessible component library for building React applications.

#### Modal Form Input with `useDisclosure`
- **`useDisclosure`**: A custom hook in Chakra UI for controlling the open/close state of a modal.
  - **`isOpen`**: Boolean value indicating if the modal is open.
  - **`onClose`**: Function to close the modal.
  - **`onOpen`**: Function to open the modal.

#### Example
```javascript
import React from 'react';
import { Button, Modal, ModalOverlay, ModalContent, ModalHeader, ModalCloseButton, ModalBody, ModalFooter, useDisclosure } from '@chakra-ui/react';

function ExpenseModal() {
  const { isOpen, onOpen, onClose } = useDisclosure();

  return (
    <>
      <Button onClick={onOpen}>Add Expense</Button>
      <Modal isOpen={isOpen} onClose={onClose}>
        <ModalOverlay />
        <ModalContent>
          <ModalHeader>Add a new expense</ModalHeader>
          <ModalCloseButton />
          <ModalBody>
            {/* Form content goes here */}
          </ModalBody>
          <ModalFooter>
            <Button colorScheme="blue" mr={3} onClick={onClose}>
              Close
            </Button>
            <Button variant="ghost">Save</Button>
          </ModalFooter>
        </ModalContent>
      </Modal>
    </>
  );
}

export default ExpenseModal;

