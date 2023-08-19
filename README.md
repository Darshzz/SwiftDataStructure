# SwiftDataStructure

This project provides a framework for commonly used data structures and algorithms written in a new iOS development language called Swift. While details of many algorithms exists on Wikipedia, these implementations are often written as pseudocode, or are expressed in C or C++. With Swift now officially released, its general syntax should be familiar enough for most programmers to understand.

Audience

As a developer, you should already be familiar with the basics of programming. Beyond algorithms, this project also aims to provide an alternative for learning the basics of Swift. This includes implementations of many Swift-specific features such as optionals, extensions, protocols and generics. Beyond Swift, audiences should be familiar with Singleton and Factory design patterns along with sets, arrays and dictionaries.

Features

The project features code-level examples for the following items:

Linked Lists
Binary Search
Insertion Sort
Bubble Sort
Selection Sort
Quick Sort
Binary Search Trees
Tree Balancing - Rotations
Stacks
Queues
Heaps & Heapsort Operations
Hash Tables
Tries
Graphs
Dijkstra's Shortest Path
Depth-First Search
Breadth-First Search
Protocol Extensions
Enumerations
Fibonacci Numbers
Generics
Dyanmic Programming
Closures
The Book

Now in its 4th edition and supporting Swift 4.2, the The Swift Algorithms Book features code and color illustrations that benefits students and professionals. As a collaborative open-source effort, I also welcome feedback and contribution from others.

Example

    //bfs traversal with inout closure function
    func traverse(_ startingv: Vertex, formula: (_ node: inout Vertex) -> ()) {

        
        //establish a new queue
        let graphQueue: Queue<Vertex> = Queue<Vertex>()
        
        
        //queue a starting vertex
        graphQueue.enQueue(startingv)
        
        
        while !graphQueue.isEmpty() {
            
            
            //traverse the next queued vertex - Swift 4.0
            //var vitem: Vertex! = graphQueue.deQueue()
            
            
            //traverse the next queued vertex
            guard var vitem = graphQueue.deQueue() else {
                break
            }
            
            //add unvisited vertices to the queue
            for e in vitem.neighbors {
                if e.neighbor.visited == false {
                    print("adding vertex: \(e.neighbor.key) to queue..")
                    graphQueue.enQueue(e.neighbor)
                }
            }
            
            //invoke formula
            formula(&vitem)

            
        } //end while
        
        
        print("graph traversal complete..")
                
    }
Getting Started

Swift Structures has been optimized for Swift 4.2 (e.g., Xcode 10.0) or later. The directories are organized as follows:

Source - Code for all Swift data structures, algorithms and source extensions
Example - An empty iOS single-view application template
SwiftTests - Unit tests with XCTest Framework
