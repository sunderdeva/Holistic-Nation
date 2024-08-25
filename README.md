Cannabis Application for Clubs
Description
Our application is designed to revolutionize the way cannabis club members interact, access information, and obtain medicinal products and services. With a focus on community and education, our app offers a comprehensive experience that covers everything from account management and rewards to event participation and access to educational resources.

Main Sections
1. User
Features
User Information: Each user can view their name, account level, and accumulated redeemable points.
Dispensation History: Allows users to view all their past dispensations.
Account Settings: Users can edit their personal information and preferences.
Token Management: Users can purchase tokens or redeem them for products and experiences within the club.
Code Example
solidity
Copiar código
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
Technologies Used
Frontend: React.js for the user interface.
Backend: Node.js with Express.js to handle server logic.
Blockchain: Scroll to manage smart contracts and transactions.
Data Encryption: To ensure user information privacy and security.
2. Support
Features
Open Question: Users can submit open questions to the organization (up to 300 characters).
Open Ticket: To report any issues or incidents.
FAQ: A basic guide with answers to common questions about the service.
Code Example
javascript
Copiar código
// Example of a contact form to submit questions and open tickets
const submitQuestion = async (question) => {
    const response = await fetch('/api/questions', {
        method: 'POST',
        headers: {
            'Content-Type': 'application/json'
        },
        body: JSON.stringify({ question })
    });
    return response.json();
};
Technologies Used
Frontend: React.js for the contact form and FAQ visualization.
Backend: Node.js with Express.js to handle question and ticket requests.
Database: MongoDB to store and manage FAQs and support tickets.
3. Medicine
Features
Product List: Users can view all available cannabis products in the club.
Dispensation Request: Allows users to describe their condition and request a cannabis dispensation, which will be reviewed by a physician.
Custom Dispensation Request: To request specific treatments with personalized medicinal products.
Code Example
javascript
Copiar código
// Example of a dispensation request submission
const submitDispensaRequest = async (request) => {
    const response = await fetch('/api/dispensas', {
        method: 'POST',
        headers: {
            'Content-Type': 'application/json'
        },
        body: JSON.stringify(request)
    });
    return response.json();
};
Technologies Used
Frontend: React.js for product display and request forms.
Backend: Node.js with Express.js to handle dispensation requests.
Database: MongoDB to store product and request information.
Blockchain: Scroll to manage smart contracts for dispensations.
4. Community
Features
Event Calendar: Allows users to view all upcoming club events.
Reserve Event Tickets: Users can reserve their event tickets using kushcoins.
Event Participation: Users can spend kushcoins to participate in club events.
Code Example
javascript
Copiar código
// Example of event ticket reservation
const reserveEvent = async (eventId, kushcoins) => {
    const response = await fetch('/api/reserve', {
        method: 'POST',
        headers: {
            'Content-Type': 'application/json'
        },
        body: JSON.stringify({ eventId, kushcoins })
    });
    return response.json();
};
Technologies Used
Frontend: React.js for event calendar and reservation display.
Backend: Node.js with Express.js to handle event reservations.
Blockchain: Scroll to manage kushcoins transactions.
5. Learning
Features
How to Grow Medicinal Plants and Herbs at Home: Instructional videos on growing medicinal plants and mushrooms.
How to Make Medicine: Detailed guides on how to prepare harvested medicinal plants for use.
Herb Wiki: A forum where users can share and discuss information about medicine and wellness.
Code Example
javascript
Copiar código
// Example of how cultivation videos are displayed
const fetchVideos = async () => {
    const response = await fetch('/api/videos');
    const videos = await response.json();
    // Render videos on the page
};
Technologies Used
Frontend: React.js for educational videos and forum visualization.
Backend: Node.js with Express.js to handle video and forum post requests.
Database: MongoDB to store videos and forum information.
User Benefits
Our application offers a complete and user-friendly experience for cannabis club members, allowing them to:

Manage their information and rewards securely and efficiently.
Access support and resolve any issues quickly.
View and request medicinal products simply.
Participate in the club community and attend events using kushcoins.
Learn how to grow and prepare their own medicines, and share knowledge in a decentralized network.
This structure provides a clear and accessible overview of all the application's features and benefits, highlighting the focus on community and education, and offering developers insight into the tools and technologies used, including code examples and integration with Scroll.
