## 🚀 GoPhish Simulation: Step-by-Step Attack Setup
"Training people, not tricking them."

Welcome to your GoPhish simulation setup guide, where we ethically create phishing simulation to raise awareness — not havoc.

### 🛠️ 1. Setting Up GoPhish

1. Go to **kali machine**
   
           bash
             gophish
   After running this `gophish` it will ask for Administrator User Password.

2.You'll be prompted to set a password (only once). After that, the tool starts running.

   If you run command again in terminal, you will see something like this.

<img width="500" height="500" alt="Screenshot from 2025-08-05 14-32-11" src="https://github.com/user-attachments/assets/b436acba-273d-44b9-b815-3dbba8b5aece" />

3. Here, you see `Opening Web UI https://127.0.0.1:3333` . This GUI will open by itself on our browser. 

You see a Dashboard like this.

<img width="1000" height="1000" alt="image" src="https://github.com/user-attachments/assets/58fcad11-ed21-495a-8761-62be07c98003" />


### 📧 2. Setting Up a Fake Gmail Account (to send emails)
> ⚠️ Use a test Gmail account. Never use your primary one.

1. Create a new Gmail account (or use an existing test account).
  
2. Enable 2-Step Verification

   <img width="1000" height="1000" alt="image" src="https://github.com/user-attachments/assets/72ced526-399e-426c-a494-37c515e92e7c" />

 Only if you have turned on 2-Step Verification, You can see App Passwords page.
 
3. Go to **App Passwords**

  <img width="1000" height="1000" alt="image" src="https://github.com/user-attachments/assets/a79af0b5-762d-4ebf-93f0-d13ed0013faf" />

> App Passwords?
>
> 

<img width="1000" height="1000" alt="image" src="https://github.com/user-attachments/assets/4b0fca67-195e-44b5-8677-d10f4186f8e3" />

4. You will see something like this,

<img width="1000" height="1000" alt="image" src="https://github.com/user-attachments/assets/17a6852f-2076-4fc9-8ee0-a657f352a392" />

5. Copy this password — we’ll use it in GoPhish.

### 📤 3. Creating a Sending Profile 

1. Go to Sending Profiles in GoPhish:
<img width="1000" height="1000" alt="image" src="https://github.com/user-attachments/assets/8ba5e527-4519-4233-984c-42d18e087631" />


<img width="1918" height="878" alt="Screenshot from 2025-08-05 15-14-50" src="https://github.com/user-attachments/assets/8b373268-57aa-4809-b3d9-cd9a053f48e3" />

2. Click **New Profile** and Fill in the details:

        Name : Friendly Alert Bot (or any name)
        SMTP From : your_fake_email@gmail.com
        Host : smtp.gmail.com:587 
        Username : your_fake_email@gmail.com
        Password : (Paste the App Password generated earlier. Note: It include spaces)

4. Click Send Test Email

Fill in the details to whome you wanna send it. **Send it to yourself**. 0_0 .

<img width="1000" height="1000" alt="image" src="https://github.com/user-attachments/assets/92309035-405c-4695-84d2-d7fcc17ec682" />

Click Send, Boom 💥. Check your mail box. 

<img width="1517" height="675" alt="image" src="https://github.com/user-attachments/assets/1ab63b30-980c-4476-8550-15f9ed544983" />


✅ Now, We are good to go.


### 🌐 4. Creating a Landing Page

> Your fake page must look legitimate enough to fool a user in a simulation.

- We need a sample page -> Victim should find it legitimate.
- Go to kali terminal

        bash
          cd /usr/share/set/src/html/templates/google
          ls
          open index. template

<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/082e34d1-0f0b-4c8d-a89b-86b095c6175f" />

  It will open something like this,

 <img width="1000" height="1000" alt="Screenshot from 2025-08-05 15-41-44" src="https://github.com/user-attachments/assets/fbe197ae-353f-4d91-8ff0-4690b0938cea" />

- Now, right click -> view page source. 

<img width="1000" height="1000" alt="image" src="https://github.com/user-attachments/assets/b1f8d37c-312e-4030-a0d9-3fdc552138c8" />

- Copy this full html code. 

- Now Go back to GoPhish Dashboard. Open Landing Page from the left side panel.-> Click New Page.

  Follow the steps:
 ( Focus: `Paste the HTML code` copied from above in the box, `Tick Mark the Checkboxes` ✅, `Fill Redirect to: https://accounts.google.com` ).

  <img width="1000" height="1000" alt="image" src="https://github.com/user-attachments/assets/097091b3-ad72-4dbc-8aa7-984a14569cf9" />

  Now You can see the listing.

  <img width="1000" height="1000" alt="image" src="https://github.com/user-attachments/assets/852a79c8-f4b6-4551-980c-43a6791e3b75" />


### 5. Email Template

- From the left panel, click Email Template

  <img width="1000" height="1000" alt="image" src="https://github.com/user-attachments/assets/df2306da-cde2-432a-a0c2-e2a854b43aec" />

- Now we need a sample mail, We can create our own and we can also take reference from another mail.
- We are importing a sample mail., Open any mail and follow the steps

  <img width="1920" height="864" alt="image" src="https://github.com/user-attachments/assets/b36170aa-34ac-4543-b0bf-01135a08dcb6" />

 <img width="1826" height="660" alt="image" src="https://github.com/user-attachments/assets/dee0a938-a6ea-4848-be4c-f55065cc5bbf" />

-After copying this, Paste it inside the Box in Email Template --> Checkmark the boxes --> Import


<img width="1918" height="878" alt="Screenshot from 2025-08-05 15-51-05" src="https://github.com/user-attachments/assets/7d216488-4eac-4af4-891f-5e298b90a1b9" />

- We'll see that we succesfully created email template.

  <img width="1918" height="878" alt="Screenshot from 2025-08-05 15-55-08" src="https://github.com/user-attachments/assets/e2bedd42-e088-4479-a619-2d3c19b7b6dc" />



### 5. Users and Groups
From here you can add group of people or can send email to single person also to whome u want to send the phishing email.

You can import Bulk users file too.

- Create New Group -> Add victims name and email id. --> Click Add --> Save Changes Once Done Adding.

<img width="1918" height="878" alt="image" src="https://github.com/user-attachments/assets/f143e609-c912-4590-9c7d-42d68a3e5fd4" />

Finally, you can see it here.

<img width="1918" height="878" alt="Screenshot from 2025-08-05 15-58-17" src="https://github.com/user-attachments/assets/9d5249a3-06ed-41fa-a33f-2b60b45b49e4" />


### 6. Create Campaign

Fill in the Details --> all of this we have created 

<img width="1918" height="878" alt="Screenshot from 2025-08-05 16-01-20" src="https://github.com/user-attachments/assets/2fd0d1a2-f4a0-431e-81dd-6451cb393589" />

Launch Campaign
<img width="1918" height="878" alt="Screenshot from 2025-08-05 16-01-37" src="https://github.com/user-attachments/assets/587242d9-356b-411e-8df3-1933ea332049" />


## Analysis on GoPhish Dashboard
<img width="1918" height="878" alt="Screenshot from 2025-08-05 16-01-49" src="https://github.com/user-attachments/assets/4e074810-77de-4b9e-971c-9979d21bf62e" />

Once user click it or enters the details , we can see it

<img width="1918" height="878" alt="image" src="https://github.com/user-attachments/assets/f5d6a547-f218-41b9-878d-4035170b6ad1" />

<img width="1918" height="878" alt="image" src="https://github.com/user-attachments/assets/e0258cdd-f71e-4006-aea7-64a9f1a4dae1" />

Once user fill in the details, We Got their credentials..

<img width="1918" height="878" alt="image" src="https://github.com/user-attachments/assets/39998fa0-8697-482b-b1f6-25be18cd55af" />

