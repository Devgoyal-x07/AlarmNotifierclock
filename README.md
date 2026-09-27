## Author

**DEV**  
Registration No.: `26BCY10129`

# â° Alarm Clock

A simple desktop alarm clock built with **Python** and **Tkinter**. Choose an hour, minute, and second from the drop-down menus, then set an alarm. When the selected time matches the computer's 24-hour clock, the app plays `sound.wav`.

## Features

- Lightweight graphical interface made with Tkinter
- Select an alarm time using hour, minute, and second menus
- Checks the current time once per second
- Plays an alarm sound when the selected time is reached

## Requirements

- Python 3
- Windows (the current version uses Python's `winsound` module)
- A WAV audio file named `sound.wav`

## Project files

```text
alarm-clock/
â”œâ”€â”€ alarm_clock.py
â”œâ”€â”€ sound.wav
â””â”€â”€ README.md
```

> If your Python script has a different name, use that filename in the run command below.

## Run the project

1. Clone or download this repository.
2. Place `sound.wav` in the same folder as the script.
3. Open a terminal in the project folder and run:

   ```bash
   python alarm_clock.py
   ```

4. Choose the alarm time and click **Set Alarm**. Use 24-hour time.

## How it works

Tkinter builds the window and time-selection menus. When **Set Alarm** is clicked, a background thread checks the selected time against the system clock every second. At a match, `winsound.PlaySound` starts playback of `sound.wav` asynchronously.

## Current limitations

- `winsound` is Windows-specific, so this version will not run unchanged on macOS or Linux.
- The current menu choices include `24` for hours and `60` for minutes and seconds; valid values are hours `00â€“23` and minutes/seconds `00â€“59`.
- There is no stop-alarm button. The sound behavior depends on the WAV file and the `winsound` playback flags.
- Clicking **Set Alarm** more than once starts additional checking threads.
- The alarm time is read by the worker thread while Tkinter controls are active; a safer implementation would transfer the selected values on the main UI thread and manage a single cancellable timer.

## Possible improvements

- Correct the time ranges and validate the selected time
- Add **Stop**, **Cancel**, and **Snooze** controls
- Prevent duplicate alarm threads and support changing the alarm
- Use a cross-platform audio library for macOS and Linux support
- Add a digital clock display and improve the interface styling

## License

Add a license file if you plan to specify how others may use, modify, or distribute this project.


