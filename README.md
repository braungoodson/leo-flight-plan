# leo-flight-plan

while (shuttle.leo.lift()) {
  if (shuttle.leo.inLeo()) {
    shuttle.payload.lift();
  }
}

// The shuttle is composed of two modules.
//  Module P for Payload Module
//  Module L for LEO Module
shuttle.payload.lift = function(coor) {
  this.engine(fcracker).ignite({
    trajectory: function() {
      return this.plan(coor);
    }
  });
};

Use the rocket engine while in leo to push the payload into zero gravity.

You can use photoelectric navigation system to target the moon and stear 
the payload with auxiliary boosters or thrusters.

