---
layout: exercise
permalink: /Modules/Scheme/Warmup/Exercise
title: "CS374: Principles of Programming Languages - Warmup with Scheme"
language: "scheme"

info:
  points: 3
  instructions: "Modify the first.scm file to square the number 5."
  goals:
    - To write a Scheme statement
    
canvasasmtid: "181953"   
canvaspoints: 3
  
processor:  
  correctfeedback: "Correct!!" 
  incorrectfeedback: "Try again"
  submitformlink: false
  feedbackprocess: | 
    var pos = feedbackString;
  correctcheck: |
    pos.toLowerCase().includes("25")
 
files:
  - filename: "first.scm"
    name: first
    ismain: false
    isreadonly: false
    isvisible: true
    code: | 
        (define square (lambda (a)
            ; TODO: Square the number here
        ))
  - filename: "main.scm"
    ismain: true
    name: main
    isreadonly: true
    isvisible: true
    code: |
        (square 5)
---
