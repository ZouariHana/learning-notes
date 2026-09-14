# Elements of a Function Contract
## Preconditions
* Constraints that client must satisfy with respect to **input arguments**, **object** or **program state**
* Otherwise behavior is undefined

## Function Behavior 
* What a function promises to do given valid input
  **Postconditions:** Return values, changes to an object or program state
  **Behavioral guarantees:** Algorithmic complexity, thread safety etc..
* Some functions do not have preconditions, for example, vector.push_back(element); vector.size();
* Others have preconditions:
   __Example__: vector.front(); //Precondition: vector should not be empty vector[index]; //Precondition: index < vector.size()
  
