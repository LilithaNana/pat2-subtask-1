# pat2-subtask-1

# What is Morse code
# Morse code is a communication system that uses a combination of dots (short signals) and dashes (long signals) to represent letters, numbers, and symbols. It was developed in the 1830s and 1840s by Samuel Morse and was mainly used for telegraph communication. Messages are sent by transmitting these signals through sound, light, radio waves, or electrical pulses. For example, the distress signal SOS is represented as ••• ––– •••. Morse code was one of the first methods of long-distance communication and played an important role in maritime, military, and emergency communications. Although it is not commonly used today, it remains an important part of the history of communication technology and is still used by some amateur radio operators.

# The history of why Morse code was created
# Morse code was created during the early 19th century when there was a growing need for faster long-distance communication. Before its invention, messages could only be delivered by physical means such as letters carried by people, horses, ships, or trains, which was often slow and inefficient. In the 1830s and 1840s, advances in electrical technology led to the development of the telegraph. Samuel Morse and his collaborators developed Morse code as a simple system that could convert letters and numbers into a series of dots and dashes. This allowed messages to be transmitted quickly over telegraph wires using electrical signals. The introduction of Morse code revolutionized communication by enabling information to be sent almost instantly across great distances. It became widely used in business, government, transportation, military operations, and emergency communications. Over time, Morse code also played a significant role in maritime and aviation communication, helping improve safety and coordination. Overall, Morse code was created to solve the problem of slow long-distance communication and became one of the most important innovations in the history of communication technology. 

# How Morse code system works
# In Morse code, each letter and number is assigned a unique pattern of dots and dashes., allowing messages to be transmitted and decoded by the sender and receiver.
#Examples:
# A = .-
# B = -...
# C = -.-.
# S = ...
# O = ---
# 1 = .----
# 2 = ..---

# A dot represents a short signal, while a dash represents a longer signal. Messages can be transmitted as sounds, light flashes, radio signals, or electrical pulses. Receive decode the sequence of dots and dashes backs into readable text. When sending a message, each letter is transmitted using its corresponding pattern of dots and dashes. Short pauses are used between the signals of a single letter, slightly longer pauses separate letters, and even longer pauses separate words.

# More Examples:
# H = ....
# E = .
# L = ._..
# L = ._..
O = ---
# Combined: •••• • •−•• •−•• −−-

#include <iostream>
#include <string>
#include <map>
#include <cctype>

using namespace std;

int main()
{
    map<char, string> morseCode = {
        {'A', ".-"}, {'B', "-..."}, {'C', "-.-."},
        {'D', "-.."}, {'E', "."}, {'F', "..-."},
        {'G', "--."}, {'H', "...."}, {'I', ".."},
        {'J', ".---"}, {'K', "-.-"}, {'L', ".-.."},
        {'M', "--"}, {'N', "-."}, {'O', "---"},
        {'P', ".--."}, {'Q', "--.-"}, {'R', ".-."},
        {'S', "..."}, {'T', "-"}, {'U', "..-"},
        {'V', "...-"}, {'W', ".--"}, {'X', "-..-"},
        {'Y', "-.--"}, {'Z', "--.."}
    };

    string message;
    string fullMorse = "";

    cout << "Enter a short message: ";
    getline(cin, message);

    cout << "\nLetter-by-Letter Translation:\n";

    for (char ch : message)
    {
        if (ch == ' ')
            continue;

        // Convert lowercase letters to uppercase
        ch = toupper(ch);

        cout << ch << ": " << morseCode[ch] << endl;

        if (!fullMorse.empty())
            fullMorse += "   ";  // Three spaces between letters

        fullMorse += morseCode[ch];
    }

    cout << "\nFull Morse Code Message:\n";
    cout << fullMorse << endl;

    return 0;
}
