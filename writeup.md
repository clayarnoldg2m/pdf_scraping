# PDF Text Extraction Project Notes

## Methods Tested

### Original Method
- **Status**: Does now extract text, and original notebook functionality is restored 
- **Next Steps**: 
  1) Likely doing a re.split on section would make sense, and then using the LLM section by section to extract Qs and As to the questionaire
  2) Then give a structured json output for the questions and answers within each section (w/ and the overall json is a list of questions)
  3) If we can get 1), then we could put the output into a txt if we want to as well

- **Drawbacks** The LLM process might not identify questions consistently between runs, potentially resulting in variable output structures.

### Attempted Method (Tables to JSON)
- **Approach**: Extract tables to json to end up with a result like this:
  ```json
  {
    "sections": [
      {
        "section name": "",
        "tables": ["json representation of table"]
      }
    ]
  }
  ```
- **Challenges**: 
  - Turned out to be difficult because they aren't "real" pdf tables
  - The syntax for section separation is not particularly reliable

## Current Progress

Some progress made, we can extract text but it's not in a perfectly intelligible way yet. To use the LLM to get Qs and As, we need to split it up, and the best method would likely be section by section, since questions within a section are related to each other.

## Open Questions

I am wondering how different the other files are from what we've processed so far. I understand that they will have the same structure, but do we need to use this file's answer descriptions to interpret the other file's answers? 

## Conclusion

We can extract text but need better section splitting to process Q&A pairs using an LLM approach.