# streamlit-subprocess
Run subprocesses with live output in Streamlit

## Installation

```bash
pip install streamlit-subprocess
```

## Usage

The following script provides live output of the command, and displays an error or success message once the command terminates:

```python
import streamlit as st
import asyncio
from streamlit_subprocess import run_subprocess

# In your Streamlit app:
if st.button("Run Command"):
    asyncio.run(run_subprocess(
        'bash',
        '-c',
        'ping -c 3 1.1.1.1 && echo "Error message" >&2 && ping -c 3 1.1.1.1'
    ))
```

## Example output

![](./docs/Streamlit%20command%20success.png)

![](./docs/Streamlit%20command%20failed.png)