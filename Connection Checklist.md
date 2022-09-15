# Camera Connection Checklist

---
### Prerequisites

- [ ] Compute Module is Power down
- [ ] All Connections are unplugged


---
### Hardware Connection 

- [ ] Unlatch Connector
- [ ] Place ribbon such that the **ribbon contacts face the Compute Module**.
    1. Blue Plastic to the outer side
    2. Metal Contact towards the inside (near Compute Module)
- [ ] Latch-in the Connector


---
### Camera Test Connection 

```bash
gst-launch-1.0 nvarguscamerasrc sensor_id=0 ! \
   'video/x-raw(memory:NVMM),width=1920, height=1080, framerate=30/1' ! \
   nvvidconv flip-method=0 ! 'video/x-raw,width=960, height=540' ! \
   nvvidconv ! nvegltransform ! nveglglessink -e
```