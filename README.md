<h1>ExpNo 1 :Developing AI Agent with PEAS Description</h1>
<h3>Name: Pharhseen Rahuman M</h3>
<h3>Register Number/Staff Id: 212224230193</h3>


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
<H3>Program</H3>

        import random
        class MedicinePrescribingAgent:
        def __init__(self):
        self.performance = 0
        self.rooms = ["Room1", "Room2"]
        self.location = random.choice(self.rooms)  # agent starts in a random room

    def sense_patient(self):
        """Sense patient condition (temperature) in the current room"""
        temperature = round(random.uniform(97.0, 103.0), 1)  # random temperature
        return temperature

    def treat_patient(self, temperature):
        """Treat patient if unhealthy"""
        if temperature > 98.5:
            print(f"Patient in {self.location} has fever ({temperature}°F). Prescribing medicine...")
            self.performance += 1  # reward for treating
        else:
            print(f"Patient in {self.location} is healthy ({temperature}°F). No medicine needed.")

    def move_to_other_room(self):
        """Move agent to the other room"""
        old_location = self.location
        self.location = self.rooms[1] if self.location == self.rooms[0] else self.rooms[0]
        print(f"Moving from {old_location} to {self.location}...")
        self.performance -= 1  # penalty for moving

    def run(self, steps=5):
        """Run the agent for given steps"""
        for step in range(steps):
            print(f"\nStep {step+1}: Agent in {self.location}")
            temp = self.sense_patient()
            self.treat_patient(temp)
            self.move_to_other_room()

        print("\nFinal Performance:", self.performance)
        agent = MedicinePrescribingAgent()
        agent.run(steps=6)

<H3>Output</H3>
<img width="702" height="576" alt="image" src="https://github.com/user-attachments/assets/512fdbd1-b10b-42cf-b9a1-5714b417c7d3" />
<H3>Result</H3>
Developing AI Agent with PEAS Description successfully
