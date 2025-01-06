import random
import subprocess
import os

def read_resolutions():
    """
    Read resolutions from a text file and pick one randomly.
    
    Returns:
    - str: A randomly selected resolution, or a default message if no resolutions are found.
    """
    file_path = '/path/to/resolutions.txt'
    if os.path.exists(file_path):
        with open(file_path, 'r') as file:
            resolutions = file.readlines()
            if resolutions:
                return random.choice(resolutions).strip()
            else:
                return "Your resolutions list is empty. Time to add some!"
    else:
        return "Resolutions file not found."

def speak(text):
    """
    Use eSpeak TTS to read the given text aloud with clear and slow speech.
    
    Parameters:
    - text (str): The text to be spoken.
    """
    try:
        # Adjust speed (-s) and pitch (-p) for clearer, slower speech
        speed = "120"  # Default is 175; lower is slower
        pitch = "50"   # Default is 50; adjust for clarity
        
        # Construct the eSpeak command
        command = ["espeak", f"-s{speed}", f"-p{pitch}", text]
        # Execute the command
        subprocess.run(command, check=True)
    except Exception as e:
        print(f"Error while using TTS: {e}")

if __name__ == "__main__":
    resolution = read_resolutions()
    speak(resolution)
