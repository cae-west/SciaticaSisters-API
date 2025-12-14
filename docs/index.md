# Sciatica Sisters API overview

Sciatica Sisters is a **REST API** for helping developers build apps that track sciatica pain. The API
lets patients store user info, track exercises, and spot patterns to take charge of their healing.

## About sciatica

Sciatica is pain that radiates along the sciatic nerve, which runs from the lower back through the hips
and down each leg. About 25% of sciatica patients experience long-term symptoms. This API provides tools
to help manage these ongoing issues through exercise tracking and pain pattern analysis.

**Learn more about sciatica:**

- [Mayo Clinic - Sciatica](https://www.mayoclinic.org/diseases-conditions/sciatica/symptoms-causes/syc-20377435)
- [Cleveland Clinic - Lower Back Pain](https://my.clevelandclinic.org/health/diseases/7936-lower-back-pain)

---

## Read first

**[Getting Started](overview/getting-started.md)** - Ready to get started? Learn what you need to set
up your system.

---

## What's an API?

An API lets different software programs talk to each other. It helps them share data and work together.

### Why use an API?

APIs help developers:

- **Build apps** without starting from zero
- **Get data** in an easy, standard way
- **Link services** across different platforms
- **Grow solutions** as more people use them

The Sciatica Sisters API handles all the data work. This lets developers focus on making great apps.

---

## Key features

### User management

- Store patient profiles
- Track age and pain location
- Check current pain levels
- Save treatment history

### Exercise tracking

- Log pain levels before and after
- Track what works over time
- Add personal notes
- Compare different treatments
- Find the best exercises

---

## API resources

The Sciatica Sisters API has two main parts:

| Resource | What It Does | Endpoint |
|----------|-------------|----------|
| **[Users](api/users.md)** | Patient profiles and pain info | `/users` |
| **[Exercise Logs](api/user-exercise-logs.md)** | Exercise tracking logs | `/userExerciseLogs` |

---

## Who should use this API?

### Healthcare apps

Build systems for therapists to track patient progress between visits.

### Wellness apps

Make apps that help people track their pain and find what helps.

### Research platforms

Study patterns in what treatments work for different people.

### Personal health trackers

Add sciatica tracking to health and wellness apps.

---

## What you can build

### Pain pattern analysis

- Link exercises to pain relief
- Track pain changes over time
- Find triggers and what helps

### Treatment plans

- Compare stretches and exercises
- Build custom plans from past data
- Adjust routines in real time

### Progress charts

- Show healing trends
- Make reports for doctors
- Keep users motivated with visuals

### Community insights

- Compare results with other users
- Find what works for similar pain
- Share success stories

---

## Core abilities

### Data you can track

**Pain metrics:**

- Pain levels on a 1 to 10 scale
- Where it hurts
- Before and after comparisons

**Exercise details:**

- Exercise name and type
- Date performed
- Personal notes
- Exercise effectiveness

### Analysis tools

**Pattern Finding:**

- See which treatments work best
- Link pain spots to helpful exercises
- Track progress over time

**Custom Plans:**

- Build plans based on what worked before
- Adjust based on pain changes
- Pick the best exercises

---

## Use case example

A person tracking their sciatica recovery:

1. **Create Profile** - Age 42, level 7 pain in lower left back
2. **Log Exercise** - Try the Piriformis Stretch
3. **Track Results** - Pain drops from 7 to 5
4. **Find Patterns** - Hip stretches give the most relief
5. **Improve Plan** - Focus on exercises that cut pain by 2+ points
