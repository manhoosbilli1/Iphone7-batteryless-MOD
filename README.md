# Iphone7-batteryless-MOD
On going research project into finding a way to use the iphone 7 without a battery like many other smart phones and laptops can be used. 


# Intro
I'm trying to modify iPhone 7 to be able to use without a battery. It's been done before on iPhone 4 successfully and I've seen some people achieve this with iPhone 6. but not iPhone 7 yet. the goal is to revive the old iPhone we have sitting around.

# Problems 
Knowing Apple the thought never crossed my mind that it would as simple as connecting power to the power connector. I was always expecting some kind of logic to be going on behind the scenes. I tried the usual methods of turning on any other android phones but they did not work. 

here is a demo of the current condition of project, [demo](https://youtube.com/shorts/5xmpZtYP9cs?feature=share)


# What I've tried
## Connected power with iPhone battery connector
4.2V line on the battery connector through a stable bench power supply. never turned on. obviously battery was removed at this point. 

## took out the battery protection circuit 
inside the battery and gave it a range of voltage 3.7-4.2V on the terminals where battery is usually attached. never turned on. 

## Used [iboot](https://www.amazon.com/Mechanic-Android-Control-Motherboard-Activation/dp/B07D37CWW3) max+ 

(inspired by qianli ipower max pro (discontinued now [ipower-link](https://www.amazon.com/-/es/Ipower-Pro-Max-reparaci%C3%B3n-compatibles/dp/B0946PBCHP)), it turned on but turns off after 2 minutes. doesn't seem to be a timed event as when computation need increases it turns off. made me think that the device might not be able to provide the surge current it needs compared to when using a battery so, 
[![iboot connected to iphone 7][1]][1]
[![iboot modul][2]][2]

## added 5V 1F cap across the battery connector with iboot max+ 
similar behaviour as before. turns of after around 2 minutes or before. restarts and so on. no luck 

## Thought to simulate battery while plugged in 
Connected  iboot max+ to iphone and connected charging cable to it's port. the iboot started making noise which made me think that iboot might not expect a reverse current since the battery  connnector also charges it. so that didn't work. 

# Conclusions up till this point 
- there is no circuitry inside a battery anymore so the phones lets iboot max+ power it on and keep it working for a few minutes but it seems like there's a certain communication going on between the battery and the phone. 
- Since it's just a simple battery seems like it's either expecting a certain resistance on the power lines
- Or some kind of response after it uses some of the power from the battery


Nothing else is coming to mind now, i do not have an oscilloscope right now to check the boot power sequence from the battery, though i think that might be helpful. 


  [1]: https://i.stack.imgur.com/8uuAC.png
  [2]: https://i.stack.imgur.com/W1e5v.png


# 8/15/2023 Thoughts 
I am now certain that the battery is designed in a way as to signal the circuit to let it know "hey i'm from apple" usually batteries of samsung and other brands are recognized when the resistance on the power line is of a certain value but this one is more complex. The only way forward now seems to be to simulate a genuine iphone battery via software and hardware. why reinvent the wheel when there is such a thing called Qianli ipower pro max+ but sadly the stock outside of china is most likely used up and no new stock in coming up. now the option is to wait for 30-40 days for the shipment to arrive or to pay extra 100-150$ for faster shipment which is not that fast as it takes between 7 to 15 days. nonetheless i'll now wait for qianli to test it out




# 2/2/2024 Reverse Engineering Qianli
I decided to go with qianli's ipower pro max to use this with. the tests were a success and the results were promising. however the circuit right now is pretty bulky. i'm trying to reverse engineeer that circuit to be able to recreate and fit it into the battery slot of iphone or the back case of iphone without too much added weight.. here's how i started to reverse engineer it. please note the resistor values are wrong but the IC names are correct. <img width="495" alt="Screenshot 2024-02-02 at 2 36 48 AM" src="https://github.com/manhoosbilli1/Iphone7-batteryless-MOD/assets/36271208/77b22ffa-42b5-41c8-b487-1f8c0d4cd68c">


