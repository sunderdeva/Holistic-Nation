# Health Organization Cannabis Application

## Description

Our application is designed to revolutionize how members of cannabis clubs interact, access information, and obtain medicinal products and services. With a focus on community and education, our app provides a comprehensive experience that covers everything from account management and rewards to event participation and access to educational resources.

## Main Sections

### 1. User

#### Features

- **User Information**: Users can view their name, account level, and accumulated redeemable points.
- **Dispensation History**: Allows users to view their past dispensations.
- **Account Settings**: Users can edit their personal information and preferences.
- **Token Management**: Users can purchase tokens or redeem them for products and experiences within the club.

#### Code Example

```solidity
// Smart contract to manage user information on Scroll
pragma solidity ^0.8.0;

contract UserInfo {
    struct User {
        string name;
        uint level;
        uint points;
    }

    mapping(address => User) private users;

    function setUser(string memory _name, uint _level, uint _points) public {
        users[msg.sender] = User(_name, _level, _points);
    }

    function getUser(address _user) public view returns (string memory, uint, uint) {
        User memory user = users[_user];
        return (user.name, user.level, user.points);
    }
}
```

#### Technologies Used

- **Frontend**: React.js for the user interface.
- **Backend**: Node.js with Express.js to handle server logic.
- **Blockchain**: Scroll to manage smart contracts and transactions.
- **Data Encryption**: Ensuring privacy and security of user information.
