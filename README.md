# One Stop Gym - Waitlist App

A responsive landing page built with **Flutter** and **Supabase**.

I built this as a test project to demonstrate a clean full-stack integration. The goal was to create a waiting list that is secure, handles data correctly, and looks good on both phones and laptops.


##  Key Features

* **Real Backend:** Connects directly to a Supabase PostgreSQL database.
* **Duplicate Handling:** I set the `email` column to *Unique* in the database. The app catches the specific Postgres error (`23505`) to tell users if they've already joined.
* **Responsive:** Used a `LayoutBuilder` to constrain the form width on desktop, so it doesn't look stretched.
* **Security:** API keys are loaded from a `.env` file (not hardcoded).

##  Tech Stack

* **Frontend:** Flutter (Web & Mobile)
* **Backend:** Supabase
* **Packages:** `supabase_flutter`, `flutter_dotenv`, `email_validator`, `google_fonts`.

##  How to Run Locally

Since I used environment variables for security, you'll need to set up the keys to run this.

1.  **Clone the repo**
    ```bash
    git clone [https://github.com/theMoeezAhmed/one-stop-gym-landing.git](https://github.com/theMoeezAhmed/one-stop-gym-landing.git)
    cd one-stop-gym-landing
    ```

2.  **Install dependencies**
    ```bash
    flutter pub get
    ```

3.  **Setup Keys**
    Create a `.env` file in the root folder and add your Supabase keys:
    ```env
    SUPABASE_URL=your_url_here
    SUPABASE_ANON_KEY=your_key_here
    ```

4.  **Run**
    ```bash
    flutter run -d chrome
    ```

##  Why I built it this way

**1. Security (`.env`)**
Coming from a backend background, I know hardcoding keys is a bad practice. I used `flutter_dotenv` to ensure the repository remains secure.

**2. Handling Duplicates**
Instead of just checking the email format, I rely on the database to enforce uniqueness. This prevents race conditions and ensures the data stays clean.

**3. UI/UX Polish**
I added a loading state to the button to prevent double-clicks and used `ScaffoldMessenger` for clear success/error feedback.
