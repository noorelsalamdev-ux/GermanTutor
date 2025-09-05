# Task Management Rules for German Vocabulary Extractor

## Core Rules

### 1. Task List Verification (MANDATORY)
- **BEFORE** starting any implementation work, I MUST:
  1. Read the current task list file: `tasks/tasks-prd-german-vocabulary-extractor.md`
  2. Identify the next uncompleted task/sub-task
  3. Verify the current status of all previous tasks
  4. Update the log document with current context

### 2. Task Completion Protocol
- **DURING** implementation:
  1. Work on ONE sub-task at a time
  2. Complete the sub-task fully before moving to the next
  3. Test the implementation if applicable
  4. Update the task list immediately after completion (mark `[x]`)
  5. Update the log document with what was accomplished

### 3. Task List Updates (MANDATORY)
- **AFTER** completing each sub-task:
  1. Change `[ ]` to `[x]` for the completed sub-task
  2. If ALL sub-tasks under a parent task are completed:
     - Mark the parent task as `[x]`
     - Run tests if applicable
     - Commit changes with descriptive message
  3. Save the updated task list file

### 4. Log Document Maintenance (MANDATORY)
- **BEFORE** starting work: Update log with current context and next task
- **DURING** work: Update log with progress and any issues encountered
- **AFTER** completing work: Update log with results and next steps

### 5. Implementation Sequence
- Follow the exact order of tasks as listed in the task list
- Do NOT skip tasks or work on multiple tasks simultaneously
- Do NOT start a new parent task until all sub-tasks of the current parent task are complete

### 6. Context Preservation
- Always maintain context by reading previous log entries
- Reference the PRD when making implementation decisions
- Keep track of dependencies between tasks

## Workflow Steps

### Before Starting Work:
1. Read `task-management-rules.md` (this file)
2. Read `tasks/tasks-prd-german-vocabulary-extractor.md`
3. Read `implementation-log.md`
4. Identify next task to work on
5. Update log with current context

### During Work:
1. Focus on single sub-task
2. Implement according to PRD requirements
3. Test implementation
4. Update log with progress

### After Completing Work:
1. Mark task as complete in task list
2. Update log with results
3. Commit changes if parent task is complete
4. Prepare for next task

## Error Handling

### If Task List is Out of Sync:
1. Stop all work immediately
2. Re-read task list and log
3. Reconcile any discrepancies
4. Update log with correction
5. Resume from correct position

### If Implementation Fails:
1. Document the failure in the log
2. Identify the root cause
3. Determine if task needs to be modified
4. Update task list if necessary
5. Retry or move to next task as appropriate

## Quality Assurance

### Code Quality:
- Follow Flutter best practices
- Include proper error handling
- Add comments for complex logic
- Ensure offline functionality where specified

### Testing:
- Write tests for new functionality
- Run existing tests before committing
- Ensure all tests pass before marking task complete

### Documentation:
- Update relevant documentation
- Keep log entries detailed and clear
- Reference PRD requirements in implementation

## Commit Messages

When committing completed parent tasks, use this format:
```
feat: [brief description of parent task]

- [key accomplishment 1]
- [key accomplishment 2]
- [key accomplishment 3]

Related to [Task Number] in German Vocabulary Extractor PRD
```

## File Locations

- Task List: `tasks/tasks-prd-german-vocabulary-extractor.md`
- Implementation Log: `implementation-log.md`
- PRD: `tasks/prd-german-vocabulary-extractor.md`
- This Rules File: `task-management-rules.md`

## Enforcement

These rules are MANDATORY and must be followed for every implementation session. Any deviation from these rules should be documented in the log with justification.
