# Trigonometry-Summative---sin-cos-tan-simulator

For every function so cos sin and tan I used the same logic and applied it to each function, so for cos lets say I use three if statements and I use np. sin, I will just replace the variables with new ones that replicate the same idea and just switch out the np.sin parts to accomodate for cos and tan

Lets look at how I approached the first part of the assaignment which was just simply making the sine, cos, and tan graphs normally. SO what I wanted to do is, is that since were technically dealing with sin, cos, and tan, it only made sense to do a pie axis. Even though it wasn't mandatory I wanted to incorperate it into my work because it would add up later and it looks more professional. I got most of the logic code from stack overflow but I changed up some things and tweaked it.

*
*
*
https://stackoverflow.com/questions/40642061/how-to-set-axis-ticks-in-multiples-of-pi-python-matplotlib - website i used for part 1
f, ax = plt.subplots(figsize = (10,5))     - essentially the f and ax represents the sizing of the graph when I plot it, this f and ax functions are basically used as variables to creat a subplot as u see I used plt. subplot. This is key when I use this graph because what happened was that if I did it without, the figure/graph would be out of control. The purpose of it is that its in control in the sense that I can make the sine graph bigger or smaller, this funciton allows me to change what is already the np.sin library as it is already made. So the subplot helps tweak it more to accomodate my graph. That is what 10 and 5 represent because those are the sizings. 

x_axis2 = np.linspace(-5 * np.pi, 5 * np. pi, 1001)   - essentially what linespace is that it makes evenly spaced out spaces so that my sin graph will come out even when being plot. The reason I do 5 is because basically its when the sine function stops so when it is reaching 5 * pi it stops and it starts at -5. Since the sin, tan and cose, functions are infinite/to large I made a scale for it. The 1001 dementrates how many times it will move, basically how many times the coordinates will. In order to make the sin function look its shape it must be above 1000 steps otherwhise it would become traingular
                                             
y_axis2 = np.cos(x_axis2) - this is calling the cos function to be plot in out x_axis2 - this is already built in the numpy library

ax.plot(x_axis2 / np.pi, y_axis2) - I do this because since I want to make my axis pie based I have to first divide the x axis numbers by pie so that then it will become all values respect to pie or turned into the pie range. I learnt this in functions where its easier for sin functions to be plotted on pie axis. I do x/pi because I simply want to represent that on my x axis, however not y because I will leave y going by 1s.

ax.xaxis.set_major_formatter(tck.FormatStrFormatter('%g $\pi$')) - I used something called tikcs which is basically something that allows me to designate points on the axis and replace them with whichever thing I want. In this case I want the pie symbol to litterly show on my axis. I got the '%g $\pi$' code from stackoverflow because they used the formatstrformatter which is basically apart of the tck libraray and that allowed me to create the symbol of pie so it would be easier for the user to understand

ax.xaxis.set_major_locator(tck.MultipleLocator(base=1.0)) - this is so it allows multiple of the points to be in that form

plt.style.use("ggplot") - this is the main function graph style called for to allow the sine function to replicate 
plt.title("Cosine Function")
plt.xlabel("X axis")
plt.ylabel("Y axis")
plt.show()

*
*
*
Ambitious Question Part: 
*
*
*
  if questionForWtvGraph1 == "equation":
      #sin function equation - using that as refrence to plot it

This is me calling all the values to put into the sin/cos/tan function for plotting which is y = a*sin(bx - c) + d
A_value1 = float(input("Enter your A value, your amplitude: "))
B_value1 = float(input("Enter your B value, your frequency: "))
C_value1 = float(input("Enter your C value, your horizontal shift: "))
D_value1 = float(input("Enter your D value, your vertical shift: "))

These two are for when user wants to stop their sin graph for running
range_Start_Value1 = int(input("Enter what number you would like for your graph to start at (starting at this point)"))
range_Stop_Value1 = int(input("Enter what number you would like to go up till on your graph: (stopping at that point) "))
       
#https://datacrayon.com/signal-processing/sine-waves-in-the-time-domain/ - used this site - it saved me 
sample_rate1 = 1000

x_axis1 = np.arange(range_Start_Value1, range_Stop_Value1, 1/sample_rate1) - similar to how I made a range in the first part, I basically did that here but I used the range values I asked the user to give me so that I could then graph them up to their expenctations. I do 1/sample_rate1 because I want it to replicate every 1 step of a thousand 

print(x_axis1)

CosineWave1 = A_value1 * np.cos(2 * np.pi * B_value1 * x_axis1 + D_value1) - this is me using the equation
print(CosineWave1)

fig = go.Figure(layout=dict(xaxis=dict(title='X axis'),yaxis=dict(title='Y axis'))) - this is basically plotting it, so plotting the x and y axis, i had to use figure because there were lots of problems with math.plot because they kept giving an error saying I have to convert to either tuples or something so I just used figure (the website did to but I understand what and why they did what they did)
fig.add_scatter(x=x_axis1, y=CosineWave1)
fig.show()
*
*
*
bullet proof part: - I just made a bunch of if statements in a giant loop so that if use enters something wrong it stops it and corrects

if questionForWtvGraph1 != "itself" and "equation":
          tryAgain1 = input("Inavlid Input. Please ReEnter again: ")
          if tryAgain1 != "itself" and "equation":
            response1 = input(print("Invalid response. Please enter itself or equation"))
            if response1 != "itself" and "equation":
              print("Thanks bye.")
            break
*
*
*
Note: I used all this logic for cos and tan to. 
