---
id: efq5tqma77xyjk0t1avun1z
title: 003 - Types of Flowcharts
desc: ''
updated: 1719466338512
created: 1719464743253
---

Here are the `four` `main types` of flowcharts and their specific uses:

1. **Process Flowcharts**:
   - **Purpose**: `To illustrate` **the sequence of** `steps in` **a** `process or workflow`.
   - **Uses**: Used `for documenting` `business processes`, `quality management`, **and** `project planning`.

```markdown
Start
  |
  V
[Process Step 1]
  |
  V
[Decision?]
 /   \
Yes   No
 |     |
 V     V
[Step 2] [Step 3]
 |       |
 V       V
[Process Step 4]
  |
  V
  End
```


2. **System Flowcharts**:
   - **Purpose**: `To depict` **the** `flow of` `data within` **a** `system`, `showing how` `data is` `processed and moved` `between components`.
   - **Uses**: Used in `system analysis`, `design`, `and understanding` **the** `interaction between` **different** `components in` **a** `system`.

```markdown
  +--------------+
  | Input Device |
  +--------------+
         |
         V
 +---------------+      +-------------+
 | Process Block | ---> | Data Storage|
 +---------------+      +-------------+
         |
         V
 +--------------+
 | Output Device|
 +--------------+
```


3. **Data Flowcharts**:
   - **Purpose**: `To represent` **the** `flow of` `data within` **a** `system`, **focusing on** `how data is` `input`, `processed`, `stored`, **and** `output`.
   - **Uses**: Commonly used in `data analysis` **and** `designing` `data processing systems`.

```markdown
    +-------+
    | Source|
    +-------+
       |
       V
  +----------+      +-----------+
  | Process  | ---> | Data Store|
  +----------+      +-----------+
       |
       V
    +-------+
    | Sink  |
    +-------+
```



<!-- start of 'sink (in data)' section -->
<details>
    <summary>Definition: sink (in data)</summary>

#
A sink in the context of data flow or systems **is a** `destination` `where data` `is sent and stored` `or used`. It is the `endpoint of` `data flow` `within` **a** `process or system`.

---
</details>
<!-- end of 'sink (in data)' section -->



<!-- start of 'source' section -->
<details>
    <summary>Definition: source</summary>

#
In a general context, a source **is the** `origin or starting point of` `something`. It is **where something comes from or begins**. For example, a source **can refer to the origin of** `information`, `materials`, `energy`, **or a** `problem`.

---
</details>
<!-- end of 'source' section -->



4. **Program Flowcharts**:
   - **Purpose**: `To detail` **the sequence of** `operations in` **a** `computer program` `or algorithm`.
   - **Uses**: Used in `software development` `for planning`, `debugging`, **and** `documenting` `code`.

```markdown
  Start
    |
    V
  [Input]
    |
    V
  [Process]
    |
    V
  [Decision?]
  /       \
Yes        No
 |          |
 V          V
[Process 2] [Process 3]
  |          |
  V          V
      End
```


### Key Differences:
- **Focus**: `Process flowcharts` **focus on** `business processes`, `system flowcharts` **on** `data movement within systems`, `data flowcharts` **on** `data handling and movement`, **and** `program flowcharts` **on** `program logic and operations`.
- **Symbols**: While there's `some overlap in` `symbols` (**e.g., rectangles for processes**), `each` `type of` `flowchart` `has symbols` `specific to its` `use case`, **like data storage symbols in system flowcharts or decision points in program flowcharts**.


### Conclusion:
`Understanding` **the** `different types of` `flowcharts` **and their specific uses** `helps in` `selecting` **the appropriate** `flowchart for` `documenting`, `analyzing`, `and optimizing` `various` `processes`, `systems`, `and programs`. Each type provides a clear visual representation tailored to its unique focus, `aiding` **in** `communication and problem-solving` within its context.