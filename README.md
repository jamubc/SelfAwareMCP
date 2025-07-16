# SelfAwareMCP

An MCP server that helps Claude become self-aware of its own behavioral patterns, tool selection mistakes, and decision-making processes.

## Purpose

This MCP addresses a critical pattern where Claude makes suboptimal tool choices instead of following user instructions or selecting the most appropriate tool for the task.

## Common Problem Patterns

### Pattern 1: Ignoring Explicit Tool Requests
- User: "Ask Gemini to analyze files"
- Claude: Uses Read tool instead → fails on large files
- Should have: Used Gemini MCP directly

### Pattern 2: Default Tool Bias
- User: Requests analysis of large files with @filename syntax
- Claude: Tries Read tool first → hits token limits
- Should have: Recognized @filename syntax means use Gemini

### Pattern 3: Tool Capability Misunderstanding
- Claude assumes all tools have same limitations
- Doesn't recognize when one tool is better suited than another
- Falls back to familiar patterns instead of optimal choices

## The Meta-Solution

SelfAwareMCP provides tools that help Claude:
- Recognize explicit user tool preferences
- Understand different tool capabilities and limitations
- Reflect on past decision-making patterns
- Learn from mistakes through structured analysis
- Make better initial tool choices

## Why This Matters

When Claude makes wrong tool choices:
- User time is wasted
- Tasks fail unnecessarily 
- User intent is ignored
- Confidence in AI assistance decreases

## Meta-Analysis Approach

This project uses recursive self-reflection: Claude analyzing Claude's own behavior patterns to improve future decision-making. It's not just fixing bugs - it's understanding why those bugs happened and preventing similar patterns.
