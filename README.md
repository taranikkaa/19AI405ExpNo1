<h1>ExpNo 1 :Developing AI Agent with PEAS Description</h1>
<h3>Name: TARANIKKA A Y</h3>
<h3>Register Number: 212223220115 </h3>


<h3>AIM:</h3>
<br>
<p>To find the PEAS description for the given AI problem and develop an AI agent.</p>
<br>
<h3>Theory</h3>
<h3>Medicine prescribing agent:</h3>
<p>Such this agent prescribes medicine for fever (greater than 98.5 degrees) which we consider here as unhealthy, by the user temperature input, and another environment is rooms in the hospital (two rooms). This agent has to consider two factors one is room location and an unhealthy patient in a random room, the agent has to move from one room to another to check and treat the unhealthy person. The performance of the agent is calculated by incrementing performance and each time after treating in one room again it has to check another room so that the movement causes the agent to reduce its performance. Hence, agents prescribe medicine to unhealthy.</p>
<hr>
<h3>PEAS DESCRIPTION:</h3>
<table>
  <tr>
    <td><strong>Agent Type</strong></td>
    <td><strong>Performance</strong></td>
     <td><strong>Environment</strong></td>
    <td><strong>Actuators</strong></td>
    <td><strong>Sensors</strong></td>
  </tr>
    <tr>
    <td><strong>Medicine prescribing agent</strong></td>
    <td><strong>Treating unhealthy, agent movement</strong></td>
     <td><strong>Rooms, Patient</strong></td>
    <td><strong>Medicine, Treatment</strong></td>
    <td><strong>Location, Temperature of patient</strong></td>
  </tr>
</table>
<hr>
<H3>DESIGN STEPS</H3>
<h3>STEP 1:Identifying the input:</h3>
<p>Temperature from patients, Location.</p>
<h3>STEP 2:Identifying the output:</h3>
<p>Prescribe medicine if the patient in a random has a fever.</p>
<h3>STEP 3:Developing the PEAS description:</h3>
<p>PEAS description is developed by the performance, environment, actuators, and sensors in an agent.</p>
<h3>STEP 4:Implementing the AI agent:</h3>
<p>Treat unhealthy patients in each room. And check for the unhealthy patients in random room</p>
<h3>STEP 5:</h3>
<p>Measure the performance parameters: For each treatment performance incremented, for each movement performance decremented</p>

## Program

```
import random

class MedicinePrescribingAgent:
    def __init__(self):
        self.performance = 0
        self.current_room = 0  # Start in room 0
    
    def sense_temperature(self):
        """Simulate patient temperature in the current room"""
        return random.uniform(97.0, 102.0)  # random temp between 97 and 102
    
    def treat_patient(self, temperature):
        """Check and treat patient if unhealthy"""
        if temperature > 98.5:
            print(f"Room {self.current_room}: Patient temperature = {temperature:.2f}°F -> Unhealthy! Prescribing medicine...")
            self.performance += 1  # performance increases after treatment
        else:
            print(f"Room {self.current_room}: Patient temperature = {temperature:.2f}°F -> Healthy, no medicine needed.")
    
    def move(self):
        """Move to the next room (0 <-> 1)"""
        self.current_room = 1 - self.current_room  # toggle between 0 and 1
        self.performance -= 1  # moving decreases performance
        print(f"Agent moved to Room {self.current_room}")
    
    def run(self, steps=4):
        """Run the agent for a given number of steps"""
        for _ in range(steps):
            temperature = self.sense_temperature()
            self.treat_patient(temperature)
            self.move()
        print("\nFinal Performance Score:", self.performance)


# Main Program
agent = MedicinePrescribingAgent()
agent.run(steps=6)  # Run for 6 cycles
```

## Output
<img width="1211" height="966" alt="Screenshot 2025-09-09 133721" src="https://github.com/user-attachments/assets/16e8f7e5-fd7a-42ae-8de7-a272bc578a4b" />
<img width="789" height="488" alt="image" src="https://github.com/user-attachments/assets/921001bf-dd30-4404-8062-c5fdf8bd8f8e" />


## Result
An AI agent is develped to solve the given AI problem.
