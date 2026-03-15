# Repository Skills

This repository provides local skills that Codex should use when the task matches their descriptions.

## Available skills

- `update-readme-on-task-complete`: Update the root `README.md` and `requirements.txt` after a thread task is completed so documentation and dependency declarations stay aligned with the latest repository structure, experiments, scripts, workflows, and runtime packages. Use when finishing implementation, fixes, reorganizations, or notebook-related tasks that may change how the repo should be understood or installed. File: `D:\jupyter_notebook\skills\update-readme-on-task-complete\SKILL.md`

## How to use

- If the user mentions the skill by name, use it.
- If a completed task materially changes repository usage, structure, setup, documented workflow, or required Python dependencies, use `update-readme-on-task-complete` before finishing.
- Read only the skill files needed for the task.
