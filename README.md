# Arcraft Maintenance Simulation
An attempt to build an airline maintenance simulation to improve the flight simulation experience based on gen-ai chat.

This project is based on the Gemini prompt, which provides information about the operations of an Airbus A340-600 in the Lufthansa.
I used this aircraft as an example of what can be done with GenAi chats. You can modify the prompt and add the operations of an airline you want.
The idea of this prompt is to teach the Gemini how the interactions between a maintenance person and a pilot could be. I'm not a pilot, so I don't know if these interactions are realistic or not, but it helps me to add some realism to my simulation.

## Project structure

This project has a prompt summary that can be used to start your chat in Gemini. It's located in the prompt **prompt-summary** folder. You can copy this prompt and paste this into Gemini chat to start.
Remember, to keep using this, you need to use the same chat to salve the context and history of the conversation. A tip is to pin this chat on Gemini.
It was created in Portuguese, I generated an English version, but I don't know if it works as expected.
Inside of **examples** folder, is an example of how to use this prompt in your simulation.

I tested the same prompt on ChatGPT, but, seems it works better on Gemini, but give it a try for ChatGPT and see the results.

Below is a general description of how it works. 
I expect it can be useful and improve your simulation.

# Aircraft Technical Log Simulation (Lufthansa A340-600)

This project simulates the operations and maintenance of Lufthansa A340-600 aircraft, maintaining a realistic technical log. The goal is to create an interactive environment for learning about aircraft maintenance procedures, the use of the MEL (Minimum Equipment List), and the importance of chronological consistency in technical records.

**Context:**

This project uses a language model to simulate the operations of Lufthansa A340-600 aircraft (exemplified by the records of D-AIHC, D-AIHI, and D-AIHU), even though these aircraft have been retired in reality. The simulation considers aspects such as:

*   **Strict Chronology:** All entries in the technical log follow a precise chronological order.
*   **Turnaround Time:** Time on the ground between flights for disembarking, embarking, refueling, and inspection.
*   **Adapted Real Routes:** Simulated routes are based on historical data of real flights operated by Lufthansa A340-600s, adapted for the simulation's present time.
*   **Occurrences and Maintenance:** Simulation of minor occurrences that would be recorded in the technical log and the respective maintenance actions.
*   **Flights without Occurrences:** Recording of flights that occurred without problems.
*   **Separation between Forecast and Record:** Clear distinction between the forecast of future flights (status and next route) and the recording of past events in the technical log.

**How to Use:**

Interaction with the simulation is done through natural language commands. Here are some examples:

*   **Request the status of an aircraft:** `What is the status of D-AIHC?`
*   **Show the technical log:** `Show me the log of D-AIHU.`
*   **Report an occurrence:** `I performed a simulated flight with D-AIHI, LH123 from FRA to SIN, on 2025-01-22 at 10:00 UTC. During descent, there was a failure in the flap system.`
*   **Simulate a flight without occurrences:** `Simulate a flight without occurrences for D-AIHC departing from MUC on 2025-01-23 at 14:00 UTC to JFK.`
*   **What is the next route of the aircraft:** `What is the next route of D-AIHU?`

**Simulation Rules:**

*   **Chronology:** Dates in the log must always be in chronological order (past to present).
*   **Turnaround:** Consider a turnaround time between flights (1-3 hours, depending on the route and airport).
*   **Technical Log:** The technical log is a *permanent* record.
*   **Forecast:** Status and next route requests are *forecasts* and do not change the log.
*   **Occurrences:** Describe occurrences in detail so they can be recorded in the log.
*   **Flights without Occurrences:** Explicitly request the simulation of a flight without occurrences to have it recorded in the log.

**Example of Technical Log (D-AIHC - Partial Example):**

| Aircraft | Date (UTC) | Location | Last Route | Landing Time (UTC) | Occurrence Description | Corrective Actions | MEL Status | Next Maintenance | Previous Maintenance | Observations |
|---|---|---|---|---|---|---|---|---|---|---|
| D-AIHC | 2025-01-15 14:00 | In flight (LH505) | GRU-MUC | N/A | Small vibration in engine 3. | To be investigated. | N/A | 2025-03-15 (MUC) | - | Reported by the pilot. |
| ... | ... | ... | ... | ... | ... | ... | ... | ... | ... | ... |

**Contributions:**

Contributions are welcome! If you have suggestions for improvements, new features, or bug fixes, feel free to open an issue or submit a pull request.

**License:**

[Add your project's license here, such as the MIT License.]

**Contact:**

[Your name/contact]
