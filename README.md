# ProductsTab Component Structure

## Overview

The **`ProductsTab`** component displays a list of invoice items in a table format. 
It allows users to view detailed information about each item through a modal and supports item deletion.

## Component Structure

### 1. ProductsTab Component

**Purpose**: The main container component that fetches and displays the list of invoice items. 
It manages the overall layout and state related to displaying items and handling user interactions.

#### Features:

- Fetches invoice data from Redux state. 

- Maps through the list of items and passes them to child components.

- Renders a **Card** with a table of items or a message if no items are present.

#### Key Responsibilities:

- Check if the invoice list is empty.
- 
- Render a message if there are no items.
- 
- Render a table if items are present.
- 
- Pass item data to **ItemRow** components.

### 2. `ItemRow` Component

#### Purpose: 

Represents a single row in the items table, displaying details for one invoice item and providing actions such as viewing details and deleting the item.

#### Features:

- Displays item details including invoice number, item name, and price.

- Provides buttons for viewing details and deleting the item.

#### Key Responsibilities:

- Display item data in table cells.

- Handle view detail button click to open a modal.

- Handle delete button click to dispatch a delete action.

- Manage the state of the modal (open/close).

### 3.`InvoiceModa`l Component

#### Purpose: 

Displays detailed information about a selected invoice item in a modal format.

#### Features:

- Shows detailed data including invoice number, date, billing information, and totals.

- Allows the user to close the modal.

#### Key Responsibilities:

- Render detailed information based on the passed item data.

- Provide functionality to close the modal.

## Component Breakdown

### `ProductsTab`

##### State/Props:

- **invoiceList** from Redux state.

- **navigate** from React Router.

##### Render Logic:

- Checks if **invoiceList** is empty.

- Displays a message if empty.

- If not empty, maps **invoiceList** to extract individual items.

- Passes item data to **ItemRow** for rendering.

##### Child Components:

    - **ItemRow**

### `ItemRow`

##### - State/Props:

- **item** object containing item details.

- **navigate** function from React Router.

##### - Render Logic:

- Displays item details in table cells.

- Provides buttons for actions (view details, delete).

- Manages the modal state (**isOpen**).

##### Child Components:

- **InvoiceModal** (conditionally rendered based on **isOpen** state).

##### `InvoiceModal`

 ##### - State/Props:

- **showModal**: Boolean to control modal visibility.

- **closeModal**: Function to close the modal.

- **info**: Object with detailed invoice information.

- **items**: Array of items to be displayed in the modal.

- **currency**, **subTotal**, **taxAmount**, **discountAmount**, total: Various financial details.

##### Render Logic:

- Displays detailed information about the selected invoice item.

- Provides functionality to close the modal.
