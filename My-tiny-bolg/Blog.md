# My IoT Journey
## Five Ideas That Changed How I See Technology and Connected Environments

## Introduction

Before taking CASA0014, my understanding of the Internet of Things (IoT) was quite limited. I associated it mainly with smart devices and convenience, such as controlling hotel curtains and lights through digital interfaces. However, the module introduced me to a broader idea: connected devices can help us measure, interpret and understand the built and natural environments around us.

Throughout the module, I gradually began to see IoT differently. The workshops, the visit to Queen Elizabeth Olympic Park and the process of developing my own prototype all challenged some of my previous assumptions about technology. Looking back, five key ideas stand out as particularly important in shaping my understanding of connected environments.

---

## 1. Starting Is More Important Than Being Ready

One of the first activities in the module involved drawing under time constraints. It made me realise that a finished result rarely comes from one perfect attempt. Instead, it develops through starting, making mistakes and improving.

I began to apply this idea to my own working habits. Previously, I treated paper notes and digital records as alternatives. Now I see that they complement each other: paper is useful for capturing ideas quickly, while digital tools help organise and preserve information.

Learning Markdown and GitHub reinforced this change. I had previously viewed GitHub mainly as a place to browse other people's projects. By working through its documentation, I gradually understood repositories, version control and tools such as `.gitignore`. These tools made it easier to organise my work and keep track of changes.

I also explored Duncan's GitHub projects to see how other developers structured and presented their work. I picked up ideas for documenting projects and sharing images through external hosting rather than placing every image file directly in the repository. This influenced how I organised the documentation for Vespera (Duncan, n.d.).

I applied this approach to Vespera Controller, developing the idea from initial sketches into a physical prototype through repeated testing. Recording the process on GitHub also helped me avoid relying entirely on memory. In previous projects, I sometimes returned to unfinished work after several weeks and struggled to remember my decisions.

I now understand prototyping as a way of thinking through action. The important thing is not to have every detail solved before beginning, but to create a process that allows ideas to develop.

<div style="display: flex; gap: 12px; align-items: center;">
  <img src="https://live.staticflickr.com/65535/55629439786_87e35d39a9_b.jpg" alt="Initial idea" style="width: 50%; height: auto;">
  <img src="https://live.staticflickr.com/65535/55628439052_e36826fd04_b.jpg" alt="Initial sketch" style="width: 50%; height: auto;">
</div>

<p><em>Initial ideas and sketches for the Vespera Controller.</em></p>

---

## 2. We Are Part of the Connected Environment

When I first thought about the environment, I imagined buildings, plants, streets and public facilities. I had not fully considered the people and wildlife that share these spaces.

While developing Vespera, I focused on creating a controller that people could understand without reading complicated instructions. This made me realise that a device is not successful simply because it works technically. Its relationship with the people using it matters just as much.

The visit to Queen Elizabeth Olympic Park expanded this understanding. One installation that caught my attention was labelled "ECHO BAT BOX". I later discovered that the Park had used automated acoustic monitoring devices to study urban bat activity. These devices capture ultrasonic calls using microphones and process the recordings to identify possible bat activity (Queen Elizabeth Olympic Park, 2017).

What interested me was that this technology was not primarily designed to make visitors' lives more convenient. Instead, it helped researchers understand wildlife that people cannot easily observe. Monitoring bat activity can provide information about urban biodiversity and environmental conditions.

I also noticed cameras and other monitoring equipment around the Park, as well as devices that appeared to measure environmental conditions such as wind. Although I could not identify the exact function of every device, their presence made me think about how much information can be collected in an ordinary public space.

This raised questions about privacy and control. Cameras may support public safety and the management of shared spaces, but who can access the information they collect? How is it used? Are people aware of what is being monitored?

These observations changed how I understand connected environments. Technology can help us understand people, wildlife and environmental conditions, but it also influences how public spaces are experienced. As Weiser and Brown (1996) suggest through the idea of calm technology, useful technology should support people's activities without constantly demanding their attention.

I now see people not simply as sources of data, but as participants and decision-makers within connected environments. Good design should consider both what technology can measure and how its presence affects the spaces we share.

<div style="display: flex; gap: 12px; align-items: center;">
  <img src="https://live.staticflickr.com/65535/55653786527_84dd581d80_b.jpg" alt="Workshop at Olympic Park" style="width: 50%; height: auto;">
  <img src="https://live.staticflickr.com/65535/55653786537_ea68508edf_b.jpg" alt="Echo Box at Olympic Park" style="width: 50%; height: auto;">
</div>

<p><em>Observations from the Olympic Park workshop, including the Echo Box.</em></p>

---

## 3. The Physical and Digital Worlds Are Not the Same

Another important lesson was realising that digital systems do not simply reproduce the physical world. Temperature, humidity and light are constantly changing, while sensors can only measure particular properties under specific conditions.

Arduino introduced me to the difference between analogue and digital inputs. Analogue inputs measure varying voltages and convert them into digital values, while digital inputs generally distinguish between states such as HIGH and LOW. The appropriate choice depends on what a system needs to detect.

I experienced the limitations of digital measurement when working with the TCS3200 colour sensor. Initially, I wanted Vespera to recognise a wide range of everyday colours. However, testing revealed inconsistent readings. The same colour could produce different results under different lighting conditions, while material and surface properties also affected the measurements.

After investigating the sensor, I learned that it does not recognise colours in the same way as human vision. Instead, it uses filtered photodiodes to measure light intensity and converts these measurements into frequency signals, which the Arduino interprets (ams OSRAM, 2018).

I therefore changed the project's scope. Rather than attempting to recognise every possible colour, I focused on four predefined colours: red, yellow, blue and green. I used an Arduino testing program to measure reference samples repeatedly and adjusted the corresponding value ranges through calibration.

This did not make the sensor universally accurate under every possible condition. Instead, it made the system more reliable for its intended application. I learned that designing a useful sensing system sometimes means reducing its ambition to match the limitations of the hardware.

This experience changed how I think about environmental data. A sensor does not provide a complete picture of reality. It measures certain properties, under particular conditions, which must then be interpreted. Digital systems do not simply reproduce reality; they measure, interpret and simplify it.

The same issue applies to smart buildings and cities. Decisions based on sensor data are only as meaningful as the measurements and interpretations behind them.

<div style="display: flex; gap: 12px; align-items: center;">
  <img src="https://live.staticflickr.com/65535/55616924880_3ba842001a_b.jpg" alt="Testing colour recognition with a mango" style="width: 50%; height: auto;">
  <img src="https://live.staticflickr.com/65535/55619335774_8e19977cfb_b.jpg" alt="Adjusting and testing sensor parameters" style="width: 50%; height: auto;">
</div>

<p><em>Colour recognition tests and sensor parameter calibration during the development of the Vespera Controller.</em></p>

---

## 4. Complexity Does Not Equal Quality

At the beginning of the Vespera project, I assumed that a more complicated product would be a better product. I imagined including multiple buttons and interaction methods to provide as many functions as possible.

However, I gradually realised that additional features could make the controller harder to understand. I therefore developed a simpler menu system using a rotary encoder and LCD. Users rotate the encoder to navigate or adjust options and press it to confirm their selections. The screen displays only the information necessary for each interaction.

I invited around five or six classmates to try the controller. After a brief demonstration, they were able to follow the same steps and operate it without much further explanation. Although this was only informal testing, it gave me some confidence that the interaction was understandable.

With additional time, I also explored the physical design of a possible future enclosure using Rhino. This allowed me to consider how the electronics might eventually fit into a more integrated and compact product. I explored the overall form and component arrangement, although the enclosure remained a digital design rather than a manufactured prototype.

This reflects human-centred design, which considers users and their needs throughout the development of interactive systems (ISO, 2019). More functions do not automatically create a better experience.

However, my small user test also has limitations. A controller that feels intuitive to several classmates may not work equally well for people with different physical abilities or levels of familiarity with technology. A more complete evaluation would require a wider range of users.

For me, the lesson is not that technology should always be simple. It is that complexity should have a purpose. Good design requires balancing technical possibilities with usability, accessibility and user control.

<div style="display: flex; gap: 12px; align-items: center;">
  <img src="https://live.staticflickr.com/65535/55618120822_00e8912ac2_b.jpg" alt="First Vespera Controller prototype" style="width: 50%; height: auto;">
  <img src="https://live.staticflickr.com/65535/55619335749_9986bdfacc_b.jpg" alt="Rhino modelling and rendering of the Vespera enclosure" style="width: 50%; height: auto;">
</div>

<p><em>From the first physical prototype to exploring a potential enclosure design in Rhino.</em></p>

---

## 5. In the Age of AI, Ideas Matter More Than Ever

AI became a useful assistant during the development of Vespera. It helped me generate the initial Arduino code and establish the basic program logic, allowing me to move more quickly towards a working prototype.

However, I did not simply accept everything it generated. I needed enough understanding of the hardware and programming logic to assess whether the proposed code was appropriate. For example, some initial menu arrangements did not match my intended interaction. I revised them according to my own design logic. Similarly, the colour calibration required repeated physical testing rather than simply accepting generated values.

I also explored an additional interaction method: voice control. Rather than trying to run voice recognition directly on the Arduino MKR WiFi 1010, I explored a separate web interface, Vespera Studio, running through a Raspberry Pi. This provided another way to select lighting options and experiment with a limited set of fixed voice commands.

The website was an exploratory extension of the project, rather than a fully developed conversational voice assistant. Nevertheless, it helped me consider how a physical controller, a web interface and a connected lighting system could work together.

This experience taught me that a limitation in one device does not necessarily mean an idea must be abandoned. Sometimes the solution is to rethink where a function should run and how different components communicate.

More importantly, I began to distinguish between implementation and design judgement. AI can accelerate coding and suggest possible solutions, but it does not automatically understand why a particular interaction should exist or what experience I want to create.

This is especially important when considering future connected environments. As technical implementation becomes more accessible, identifying meaningful problems and understanding people's needs may become even more valuable. Kitchin (2014) also reminds us that data-driven urban systems raise questions about governance, surveillance and control.

For me, embracing AI means using it to expand what I can explore, not allowing it to replace my curiosity or judgement. AI can help me start more quickly, but I still need to decide where to start and why.

<figure>
  <img src="https://live.staticflickr.com/65535/55653816982_67e33345d2_b.jpg" alt="Vespera Studio website interface" style="width: 100%; height: auto;">
  <figcaption><em>Vespera Studio: a web-based interface explored as an additional way to interact with the Vespera Controller.</em></figcaption>
</figure>

---

## Conclusion

My understanding of IoT has moved beyond the idea of connecting devices for convenience. I now see connected devices as tools that help us notice changes, interpret information and interact with the environments around us.

From observing environmental monitoring equipment in Olympic Park to testing the limitations of my own colour sensor, I have realised that collecting data is only one part of understanding an environment. We must also consider how technology affects people, wildlife and the spaces they share.

The most important lesson I will take from this module is that meaningful ideas develop through observation, experimentation and action. Technology can help us make sense of the world, but it is people who give that process direction.

---

## Project Links

- [Vespera Controller — GitHub repository](https://github.com/Leocean22/casa0014-vespera-controller)
- [Vespera Controller — Development photographs](https://www.flickr.com/photos/205099843@N04/albums/72177720336358707/)
- [CASA0014 — Connected Environments course materials](https://github.com/ucl-casa-ce/casa0014)

## References

ams OSRAM (2018) *TCS3200: Programmable Color Light-to-Frequency Converter*. Datasheet, version 1-01.

Duncan (n.d.) GitHub profile. Available at: https://github.com/djdunc (Accessed: 15 November 2026).

International Organization for Standardization (ISO) (2019) *ISO 9241-210:2019 Ergonomics of human-system interaction — Part 210: Human-centred design for interactive systems*. Geneva: ISO.

Kitchin, R. (2014) ‘The real-time city? Big data and smart urbanism’, *GeoJournal*, 79, pp. 1–14. https://doi.org/10.1007/s10708-013-9516-8.

Queen Elizabeth Olympic Park (2017) ‘Smart detectors to monitor urban bat life’. 29 June. Available at: https://www.queenelizabetholympicpark.co.uk/our-stories/smart-detectors-monitor-urban-bat-life (Accessed: 15 November 2026).


Weiser, M. and Brown, J.S. (1996) ‘The coming age of calm technology’. Xerox PARC.