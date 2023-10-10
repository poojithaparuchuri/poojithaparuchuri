## Flowchart for Finding All Sequence Lengths in a FASTA Dataset

```mermaid
graph TD;
    A(Start) --> B{More lines in the file?};
    B -- Yes --> C{Line starts with '>'?};
    C -- Yes --> D[Parse sequence name from line];
    C -- No --> E[Calculate length of the sequence line];
    D --> F[Reset sequence_length to 0];
    E --> G[Add length to sequence_length];
    G --> B;
    F --> H{Next line starts with '>'?};
    H -- Yes --> I[Add entry to sequence_lengths dictionary];
    H -- No --> D;
    I --> J[Print results in the desired format (e.g., 'sequence_name sequence_length')];
    J --> K[Close the file];
    K --> L(End);
