# bkchodi
const [isChecked, setIsChecked] = useState(false);

  const handleCheckboxChange = (event: React.ChangeEvent<HTMLInputElement>) => {
    setIsChecked(event.target.checked);
  };
 <input
    type="checkbox"
    checked={isChecked}
    onChange={handleCheckboxChange}
  />
  import React, { useState } from 'react';

interface ListItem {
  id: number;
  name: string;
  isChecked: boolean;
}

const TableWithCheckboxes: React.FC = () => {
  const [dataList, setDataList] = useState<ListItem[]>([
    { id: 1, name: 'Item 1', isChecked: false },
    { id: 2, name: 'Item 2', isChecked: false },
    { id: 3, name: 'Item 3', isChecked: false },
    // Add more items as needed
  ]);

  const handleCheckboxChange = (itemId: number) => {
    const updatedList = dataList.map(item => {
      if (item.id === itemId) {
        return {
          ...item,
          isChecked: !item.isChecked,
        };
      }
      return item;
    });

    setDataList(updatedList);
  };

  const handleButtonClick = () => {
    const requiredItemsChecked = dataList.every(item => item.isChecked);

    if (!requiredItemsChecked) {
      alert('Please check all required checkboxes.');
      // You can show a popup or display an error message here
    } else {
      // Perform further actions if all required checkboxes are checked
    }
  };

  return (
    <div>
      <table>
        <thead>
          <tr>
            <th>ID</th>
            <th>Name</th>
            <th>Checkbox</th>
          </tr>
        </thead>
        <tbody>
          {dataList.map(item => (
            <tr key={item.id}>
              <td>{item.id}</td>
              <td>{item.name}</td>
              <td>
                <input
                  type="checkbox"
                  checked={item.isChecked}
                  onChange={() => handleCheckboxChange(item.id)}
                />
              </td>
            </tr>
          ))}
        </tbody>
      </table>
      <button onClick={handleButtonClick}>Submit</button>
    </div>
  );
};

export default TableWithCheckboxes;

  import React, { useState } from 'react';

interface ListItem {
  id: number;
  name: string;
  isChecked: boolean;
}

const TableWithCheckboxes: React.FC = () => {
  const [dataList, setDataList] = useState<ListItem[]>([
    { id: 1, name: 'Item 1', isChecked: false },
    { id: 2, name: 'Item 2', isChecked: false },
    { id: 3, name: 'Item 3', isChecked: false },
    // Add more items as needed
  ]);

  const handleCheckboxChange = (itemId: number) => {
    const updatedList = dataList.map(item => {
      if (item.id === itemId) {
        return {
          ...item,
          isChecked: !item.isChecked,
        };
      }
      return item;
    });

    setDataList(updatedList);
  };

  const handleButtonClick = () => {
    const requiredItemsChecked = dataList.every(item => item.isChecked);

    if (!requiredItemsChecked) {
      alert('Please check all required checkboxes.');
      // You can show a popup or display an error message here
    } else {
      // Perform further actions if all required checkboxes are checked
    }
  };

  return (
    <div>
      <table>
        <thead>
          <tr>
            <th>ID</th>
            <th>Name</th>
            <th>Checkbox</th>
          </tr>
        </thead>
        <tbody>
          {dataList.map(item => (
            <tr key={item.id}>
              <td>{item.id}</td>
              <td>{item.name}</td>
              <td>
                <input
                  type="checkbox"
                  checked={item.isChecked}
                  onChange={() => handleCheckboxChange(item.id)}
                />
              </td>
            </tr>
          ))}
        </tbody>
      </table>
      <button onClick={handleButtonClick}>Submit</button>
    </div>
  );
};

export default TableWithCheckboxes;
