## Setting Up an Email Server Using Cisco Packet Tracer

In this lab, I will guide you through the process of setting up an email server in Cisco Packet Tracer, complete with two PCs configured to send and receive emails. Our email users, `user1@gmail.com` and `user2@gmail.com`, will communicate via SMTP and POP3 protocols.

#### Step 1: Network Topology Setup

To get started, we need to create a basic network topology:

1. Open Cisco Packet Tracer and create a new project.
2. Add the following devices to the workspace:
    - **1 Server** (to act as the email server)
    - **2 PCs** (PC0 and PC1)
    - **1 Switch**
3. Use Copper Straight-Through cables to connect the devices to the switch.

#### Step 2: Configure the Server

1. **Assign an IP Address to the Server:**
    
    - Click on the server.
    - Go to the **Desktop** tab and select **IP Configuration**.
    - Set the IP address to `192.168.1.100` and the subnet mask to `255.255.255.0`.
2. **Enable Email Services:**
    
    - Switch to the **Services** tab on the server.
    - Select **Email** from the left menu.
    - Enable the **SMTP** and **POP3** services.
    - Add the users:
        - `user1@gmail.com` with a password (e.g., `123`)
        - `user2@gmail.com` with a password (e.g., `123`)

#### Step 3: Configure the PCs

1. **Assign IP Addresses:**
    
    - For PC0, set the IP address to `10.0.0.5` and the default gateway to `10.0.0.1`.
    - For PC1, set the IP address to `10.0.0.10` and the default gateway to `10.0.0.1`.
2. **Configure Email Clients:**
    
    - Open the **Email** application on each PC.
    - Configure the email settings for PC0:
        - Email: `user1@gmail.com`
        - Password: `123`
        - Incoming Mail Server (POP3): `192.168.1.100`
        - Outgoing Mail Server (SMTP): `192.168.1.100`
    - Configure the email settings for PC1:
        - Email: `user2@gmail.com`
        - Password: `123`
        - Incoming Mail Server (POP3): `192.168.1.100`
        - Outgoing Mail Server (SMTP): `192.168.1.100`

#### Step 4: Test the Email Communication

1. **Sending an Email:**
    
    - On PC0, open the email application and compose a new email:
        - Recipient: `user2@gmail.com`
        - Subject: "Test Email"
        - Body: "Hello from User1."
    - Click **Send**.
2. **Receiving the Email:**
    
    - On PC1, open the email application and click **Receive** to check for new emails.
    - Verify that the email from `user1@gmail.com` is received.
3. **Replying to the Email:**
    
    - On PC1, reply to the email with a new message:
        - Subject: "Reply to Test Email"
        - Body: "Hello User1, message received."
    - Send the email.
    - On PC0, click **Receive** to verify the reply is received.

#### Conclusion

If you want to learn more about "How email works" and the "Security implemented" for email.

Check out these two blogs below:
- https://medium.com/@tech-n0/behind-the-scenes-how-emails-travel-faster-than-gossip-a48ac636d8b5
- https://medium.com/@tech-n0/email-spoofing-unmasked-spf-dkim-dmarc-to-the-rescue-650529dad986

This exercise is a great way to understand email protocols and server-client configurations in a controlled network environment. Happy networking!