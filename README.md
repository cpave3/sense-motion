# Motion Sense

This library provides a standard interface for reading data from mobile device motion sensors
across a range of devices.

## Why is this a thing?

In my efforts to find a simple way to read Gyroscope data on mobile devices regardless of platform or browser, 
discovered that while there are things like the Generic Sensor API, not all browsers and not all platforms support such things.

I needed a way to simply set a user-defined frequency, and read data from the motion sensor at that rate. To this end, motion-sense was created.

## How to use?

Setting up a new instance of motion-sense is easy. Once the file is included or required, you can instantiate a new sensor like so:

```
// Create a new instance
var gyro = new Motion.Gyroscope({ frequency: 30 }); // Set your desired sample read-frequency

// Set up an event listener to do something with the data once it comes through
gyro.addEventListener('reading', function(event) {
    console.log(event.detail.rotationRate)
});

// Start reading from the sensor
gyro.start();

// Stop reading when you are done
setTimeout(gyro.stop(), 5000);
```

### Supported Methods

All sensors in this library support the same set of methods.

  - start()
  - stop()
