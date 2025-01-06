# Internet Speed Checker

This project is a simple web-based internet speed checker that allows users to test their download and upload speeds. The application fetches data from external servers to measure the time taken for a file transfer, calculates the speed, and displays the results in terms of average and maximum download and upload speeds.

## Features

- **Interactive UI**: Clean and modern interface that allows users to check their internet speed with a single click.
- **Animated Background**: A gradient animation that provides an engaging user experience.
- **Confetti Effect**: After the test completes, confetti is triggered to celebrate the results.
- **Download and Upload Speed Testing**: The application measures both download and upload speeds over a 5-second duration and calculates the average and maximum values.
- **Progress Bar**: A progress bar indicates the current status of the speed test.

## Technologies Used

- **HTML**: Used for structuring the content and defining the layout of the page.
- **CSS**: Applied for styling, animations, and responsiveness.
  - **CSS Grid** and **Flexbox** for layout design.
  - **Keyframe Animation** for the background gradient animation.
- **JavaScript**:
  - Used for the speed test logic, calculating download/upload speeds, and updating the progress bar in real time.
  - **Canvas Confetti** library for the confetti effect when the speed test finishes.
- **External Resources**:
  - **Google Fonts**: Roboto font for typography.
  - **Canvas Confetti**: A library for creating a fun confetti animation (used to trigger celebratory effects at the end of the speed test).
  
## How It Works

### 1. **UI Layout**:
   - The application consists of a central container with:
     - A heading that asks the user to check their internet speed.
     - A "Check Now" button to initiate the test.
     - A progress bar that displays while the test is running.
     - A result section that shows the average and maximum download/upload speeds after the test completes.
   
### 2. **Speed Testing Process**:
   - **Initiating the Test**: When the user clicks the "Check Now" button, the `checkSpeed()` function is invoked. This function:
     - Hides the result section and shows the progress bar.
     - Starts two simultaneous tests: one for download speed and one for upload speed.
   
   - **Download Test**: For the download test, the code fetches a file (a PNG image) from Wikimedia. The time taken for the file to transfer is measured, and the download speed is calculated using the file size and time duration.
   
   - **Upload Test**: For the upload test, the code sends a small data payload (a 50KB blob) to a test server (httpbin.org). The time taken to upload the data is measured, and the upload speed is calculated similarly.
   
   - **Calculating Results**: Both download and upload tests run for a duration of 5 seconds. The speeds are calculated multiple times within this period, and the average and maximum speeds are derived.

### 3. **Progress Bar**:
   - As the tests run, the progress bar is updated to show the current progress of the tests.

### 4. **Displaying Results**:
   - After both tests are completed, the results are displayed, showing the average and maximum download and upload speeds.
   - Confetti is triggered at both the bottom-left and bottom-right corners of the screen to celebrate the completion of the test.
