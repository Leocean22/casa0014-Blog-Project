# My IoT Journey
## Five Ideas That Changed How I See Technology and Connected Environments

## Introduction

Before taking CASA0014, my understanding of the Internet of Things (IoT) was quite limited. I associated it mainly with smart devices and convenience, such as controlling hotel curtains and lights through digital interfaces. However, the module introduced me to a broader idea: connected devices can help us measure, interpret and understand the built and natural environments around us.

The workshops, the visit to Queen Elizabeth Olympic Park and the process of developing my own prototype all challenged some of my previous assumptions about technology. Looking back, five key ideas stand out as particularly important in shaping my understanding of connected environments. Through these experiences, I came to see that IoT is not simply about connecting devices or collecting data, but about helping people interpret and interact with the environments around them, while recognising how technology can also shape those environments.

---

## 1. Starting Is More Important Than Being Ready

One of the first activities in the module involved drawing under time constraints. It made me realise that a finished result rarely comes from one perfect attempt. Instead, it develops through starting, making mistakes and improving.

I began to apply this idea to my own working habits. I realised that paper notes and digital records complement each other: paper helps me capture ideas quickly, while digital tools help me organise and preserve them. Learning Markdown and GitHub also introduced me to repositories, version control and tools such as `.gitignore`, which helped me manage my work and track changes.

I also referred to the CASA0014 Vespera repository to understand how the original lighting system was organised and documented. Its README explains how the luminaire, Arduino dial, MQTT broker and web visualiser work together as parts of a connected system. These examples influenced how I documented my own controller and explained its relationship with the wider Vespera system. The repository credits Duncan Wilson for the original workshop sketches and MQTT communication model (UCL CASA-CE, n.d.).

I applied this approach to Vespera Controller, developing the idea from initial sketches into a physical prototype through repeated testing. Recording the process on GitHub helped me keep track of my decisions and avoid relying entirely on memory. Through this process, I came to understand prototyping as a way of thinking through action rather than simply producing a finished object. Starting with an imperfect idea allows me to discover problems that I might not have anticipated through planning alone.

<div style="display: flex; gap: 16px; align-items: flex-start; justify-content: center; flex-wrap: wrap;">
  <img src="https://live.staticflickr.com/65535/55629439786_87e35d39a9_b.jpg" alt="Initial idea" style="width: 48%; height: auto; object-fit: contain;">
  <img src="https://live.staticflickr.com/65535/55628439052_e36826fd04_b.jpg" alt="Initial sketch" style="width: 48%; height: auto; object-fit: contain;">
</div>

<p style="text-align: center;"><em>Initial ideas and sketches for the Vespera Controller.</em></p>

---

## 2. We Are Part of the Connected Environment

While developing Vespera, I focused on creating a controller that people could understand without reading complicated instructions. This made me realise that a device is not successful simply because it works technically. Its relationship with the people using it matters just as much.

The visit to Queen Elizabeth Olympic Park expanded this understanding. One installation that caught my attention was labelled "ECHO BAT BOX". I later found that Queen Elizabeth Olympic Park had also used automated acoustic monitoring devices to study urban bat activity. These devices capture ultrasonic calls using microphones and process the recordings to identify possible bat activity (Queen Elizabeth Olympic Park, 2017).

What interested me was that this technology was not primarily designed to make visitors' lives more convenient. Instead, it helped researchers understand aspects of the natural environment that people cannot easily observe. Monitoring bat activity can provide information about urban biodiversity and environmental conditions. The article also explains that captured audio was deleted after the bat-related results had been extracted. This made me consider how data processing and data retention decisions can influence privacy in connected environments.

I also noticed cameras and other monitoring equipment around the Park, which made me consider how much information can be collected in public spaces. Although such devices may support public safety and the management of shared spaces, their presence also raises questions about who can access the collected information and how it is used.

These observations changed how I understand connected environments. Technology can help us understand people, wildlife and environmental conditions, but it also influences how public spaces are experienced and managed. Weiser and Brown's (1996) idea of calm technology suggests that technology should support people's activities without constantly demanding their attention. However, being unobtrusive should not mean being invisible or beyond people's understanding. People should not be treated simply as sources of data; they should be able to understand and participate in the environments shaped by connected technologies. Good design must therefore consider who technology serves and how it affects the spaces we share.

<div style="display: flex; gap: 16px; align-items: flex-start; justify-content: center; flex-wrap: wrap;">
  <img src="https://live.staticflickr.com/65535/55653786527_84dd581d80_b.jpg" alt="Workshop at Olympic Park" style="width: 48%; height: auto; object-fit: contain;">
  <img src="https://live.staticflickr.com/65535/55653786537_ea68508edf_b.jpg" alt="Echo Box at Olympic Park" style="width: 48%; height: auto; object-fit: contain;">
</div>

<p style="text-align: center;"><em>Observations from the Olympic Park workshop, including the Echo Box.</em></p>

---

## 3. The Physical and Digital Worlds Are Not the Same

Another important lesson was realising that digital systems do not simply reproduce the physical world. Temperature, humidity and light are constantly changing, while sensors can only measure particular properties under specific conditions.

I experienced the limitations of digital measurement when working with the TCS3200 colour sensor. Initially, I wanted Vespera to recognise a wide range of everyday colours. However, testing revealed inconsistent readings. The same colour could produce different results under different lighting conditions, while material and surface properties also affected the measurements.

After investigating the sensor, I learned that it does not recognise colours in the same way as human vision. Instead, it uses filtered photodiodes to measure light intensity and converts these measurements into frequency signals, which the Arduino interprets (ams OSRAM, 2018).

I therefore changed the project's scope. Rather than attempting to recognise every possible colour, I focused on four predefined colours: red, yellow, blue and green. I used an Arduino testing program to measure reference samples repeatedly and adjusted the corresponding value ranges through calibration.

This did not make the sensor universally accurate under every possible condition. Instead, it made the system more reliable for its intended application. I learned that designing a useful sensing system sometimes means reducing its ambition to match the limitations of the hardware.

This experience changed how I think about environmental data. I realised that sensor readings are not neutral representations of reality; they are shaped by what a device is designed to measure, the conditions in which it operates and the way its readings are interpreted. Digital systems therefore do not simply reproduce reality. They select, measure and simplify particular aspects of it. This means that understanding an environment requires more than collecting data; it also requires questioning what the data represents and what it leaves out.


<div style="display: flex; gap: 16px; align-items: flex-start; justify-content: center; flex-wrap: wrap;">
  <img src="https://live.staticflickr.com/65535/55616924880_3ba842001a_b.jpg" alt="Testing colour recognition with a mango" style="width: 48%; height: auto; object-fit: contain;">
  <img src="https://live.staticflickr.com/65535/55619335774_8e19977cfb_b.jpg" alt="Adjusting and testing sensor parameters" style="width: 48%; height: auto; object-fit: contain;">
</div>

<p style="text-align: center;"><em>Colour recognition tests and sensor parameter calibration during the development of the Vespera Controller.</em></p>

---

## 4. Complexity Does Not Equal Quality

At the beginning of the Vespera project, I assumed that a more complicated product would be a better product. I imagined including multiple buttons and interaction methods to provide as many functions as possible.

However, I gradually realised that additional features could make the controller harder to understand. I therefore developed a simpler menu system using a rotary encoder and LCD. Users rotate the encoder to navigate or adjust options and press it to confirm their selections. The screen displays only the information necessary for each interaction.

I invited around five or six classmates to try the controller. After a brief demonstration, they were able to follow the same steps and operate it without much further explanation. Although this was only informal testing, it gave me some confidence that the interaction was understandable.

I also explored a possible enclosure design using Rhino. Although I did not manufacture it, the model helped me consider how the physical arrangement of components could affect usability. This connects to human-centred design, which considers users and their needs throughout the development of interactive systems (ISO, 2019).

However, my small user test also has limitations. A controller that feels intuitive to several classmates may not work equally well for people with different physical abilities or levels of familiarity with technology. A more complete evaluation would require a wider range of users.

For me, the lesson is not that technology should always be simple. It is that complexity should have a purpose. Good design requires balancing technical possibilities with usability, accessibility and user control.

<div style="display: flex; gap: 16px; align-items: flex-start; justify-content: center; flex-wrap: wrap;">
  <img src="https://live.staticflickr.com/65535/55618120822_00e8912ac2_b.jpg" alt="First Vespera Controller prototype" style="width: 48%; height: auto; object-fit: contain;">
  <img src="https://live.staticflickr.com/65535/55619335749_9986bdfacc_b.jpg" alt="Rhino modelling and rendering of the Vespera enclosure" style="width: 48%; height: auto; object-fit: contain;">
</div>

<p style="text-align: center;"><em>From the first physical prototype to exploring a potential enclosure design in Rhino.</em></p>

---

## 5. In the Age of AI, Ideas Matter More Than Ever

During the development of Vespera, AI helped me generate the initial Arduino code and establish the basic program logic, allowing me to move more quickly towards a working prototype.

However, I did not simply accept everything it generated. I needed enough understanding of the hardware and programming logic to assess whether the proposed code was appropriate. For example, some initial menu arrangements did not match my intended interaction. I revised them according to my own design logic. Similarly, the colour calibration required repeated physical testing rather than simply accepting generated values.


I also explored voice control through Vespera Studio, a web interface running on a Raspberry Pi. Rather than running voice recognition directly on the Arduino MKR WiFi 1010, I used this separate interface to experiment with a limited set of fixed voice commands. This showed me how limitations in individual devices can be addressed by distributing tasks across a connected system, with the Arduino, Raspberry Pi and web interface each performing different roles.

More importantly, I began to distinguish between implementation and design judgement. AI can accelerate coding and suggest possible solutions, but it does not automatically understand why a particular interaction should exist or what experience I want to create.

As technical implementation becomes more accessible, identifying meaningful problems and understanding people's needs may become even more valuable. Kitchin (2014) reminds us that data-driven urban systems also raise questions about governance, surveillance and control. For me, AI should expand what I can explore, not replace my curiosity or judgement. It can help me implement an idea more quickly, but I must still decide what is worth creating and why.

<figure style="text-align: center; margin: 20px auto;">
  <img src="https://live.staticflickr.com/65535/55653816982_67e33345d2_b.jpg" alt="Vespera Studio website interface" style="width: 85%; max-width: 800px; height: auto; object-fit: contain;">
  <figcaption><em>Vespera Studio: a web-based interface explored as an additional way to interact with the Vespera Controller.</em></figcaption>
</figure>

---

## Conclusion

My understanding of IoT has moved beyond the idea of connecting devices for convenience. I now see connected devices as tools that help us notice changes, interpret information and interact with the environments around us. However, understanding these environments also means considering how technology affects people, biodiversity and the shared spaces in which they live.

The most important lesson I will take from this module is that meaningful ideas develop through observation, experimentation and action. Connected technologies can help us understand our surroundings, but their value ultimately depends on how thoughtfully we design them, whose needs they serve and how they shape the environments we share.

---

## Project Links

- [Vespera Controller — My GitHub repository](https://github.com/Leocean22/casa0014-vespera-controller)
- [Vespera Controller — Development photographs](https://www.flickr.com/photos/205099843@N04/albums/72177720336358707/)
- [CASA0014 — Course GitHub repository](https://github.com/ucl-casa-ce/casa0014)
- [CASA0014 — Vespera project README](https://github.com/ucl-casa-ce/casa0014/blob/main/vespera/readme.md)

---

## References

- ams OSRAM (2018) *TCS3200: Programmable Color Light-to-Frequency Converter*. Datasheet, version 1-01, 14 March. Available at: https://look.ams-osram.com/m/664723bdb31f55db/original/TCS3200-DS000107.pdf (Accessed: 16 November 2026).

- International Organization for Standardization (2019) *ISO 9241-210:2019 Ergonomics of human-system interaction — Part 210: Human-centred design for interactive systems*. Available at: [https://www.iso.org/standard/77520.html](https://www.iso.org/standard/77520.html) (Accessed: 16 November 2026).

- Kitchin, R. (2014) ‘The real-time city? Big data and smart urbanism’, *GeoJournal*, 79, pp. 1–14. Available at: [https://doi.org/10.1007/s10708-013-9516-8](https://doi.org/10.1007/s10708-013-9516-8).

- Queen Elizabeth Olympic Park (2017) ‘Smart detectors to monitor urban bat life’, 29 June. Available at: [https://www.queenelizabetholympicpark.co.uk/our-stories/smart-detectors-monitor-urban-bat-life](https://www.queenelizabetholympicpark.co.uk/our-stories/smart-detectors-monitor-urban-bat-life) (Accessed: 16 November 2026).

- UCL CASA-CE (n.d.) *Vespera README*. Available at: [CASA0014 Vespera documentation](https://github.com/Leocean22/casa0014-vespera-controller) (Accessed: 16 November 2026).

- Weiser, M. and Brown, J.S. (1996) *The Coming Age of Calm Technology*. Xerox PARC, 5 October. Available at: [https://calmtech.com/papers/coming-age-calm-technology](https://calmtech.com/papers/coming-age-calm-technology) (Accessed: 16 November 2026).