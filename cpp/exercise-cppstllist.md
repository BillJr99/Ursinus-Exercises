---
layout: exercise
language: "cpp"
permalink: /Modules/Cpp/STLList
title: "CS174: STL List Class Exercise"
excerpt: "CS174: STL List Class Exercise"
canvasasmtid: "144446"
canvaspoints: "1.5"
canvashalftries: 5

info:
  points: 1.5
  instructions: "In addition to a push_back method, the STL list class also has a push_front method to add things to the front of a list in constant time (i.e. without having to loop), regardless of the list size.  Use this method to fill a list with the reverse of the elements in another list"
  goals:
    - Work classes and objects in C++
    - Work with dynamic object references in C++
    - Work with STL classes in C++
    
processor:  
  correctfeedback: "Correct!!" 
  incorrectfeedback: "Try again"
  submitformlink: false
  feedbackprocess: | 
    var pos = runtime.text.trim();
  correctcheck: |
    pos.includes("81 64 49 36 25 16 9 4 1 0")
  incorrectchecks:
    - incorrectcheck: |
        pos.includes("4, 5, 6")
      feedback: "Try again.  It looks like you're still only adding elements at the end."
 
files:
  - filename: "student.cpp"
    name: student
    ismain: false
    isreadonly: false
    isvisible: true
    height: 500
    code: | 
        #include <stdio.h>
        #include <list>

        using namespace std;

        class IntWrapper {
            public:
                int x;
                IntWrapper(int x) {
                    this->x = x;
                }
        };
        
        /**
        * @brief Copy all of the elements from arr into arrRev in reverse
        * order by using the push_front method of the stl list
        * 
        * @param arr Original linked list
        * @param arrRev Linked list that will hold the reverse of the elements
        */
        void copyRev(list<IntWrapper*>& arr, list<IntWrapper*>& arrRev) {
            // TODO: Fill this in
        }


  - filename: "main.cpp"
    name: main
    ismain: true
    isreadonly: true
    isvisible: true
    code: | 
        int main(int argc, char** argv) {
            int N = 10;
            list<IntWrapper*> arr;
            for (int i = 0; i < N; i++) {
                arr.push_back(new IntWrapper(i*i));
            }
            list<IntWrapper*> arrRev;
            copyRev(arr, arrRev);
            list<IntWrapper*>::iterator it;
            for (it = arrRev.begin(); it != arrRev.end(); it++) {
                IntWrapper* x = *it;
                printf("%i ", x->x);
            }
            printf("\n");
            for (it = arr.begin(); it != arr.end(); it++) {
                IntWrapper* x = *it;
                delete x;
            }
            return 0;
        }
openFilesOnLoad: ["driver.cpp", "student.cpp"]        
---
