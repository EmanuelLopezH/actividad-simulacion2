# Actividad de seguimiento - Simulación 2

| Integrante            | correo                     | usuario github |
| --------------------- | -------------------------- | -------------- |
| Emanuel López Higuita | emanuel.lopezh@udea.edu.co | EmanuelLopezH  |
| Andres Calvo Areiza   | andres.calvoa@udea.edu.co  | andres-calvo   |

## Instrucciones

Antes de empezar a realizar esta actividad haga un **fork** de este repositorio y sobre este trabaje en la solución de las preguntas planteadas en la actividad de simulación. Las respuestas deben ser respondidas en español o si lo prefiere en ingles en el lugar señalado para ello (La palabra **answer** muestra donde).

## Homework (Simulation)

This program, [mlfq.py](mlfq.py), allows you to see how the MLFQ scheduler presented in this chapter behaves. See the [README](https://github.com/remzi-arpacidusseau/ostep-homework/blob/master/cpu-sched-mlfq/README.md) for details.

### Questions

1.  Run a few randomly-generated problems with just two jobs and two queues; compute the MLFQ execution trace for each. Make your life easier by limiting the length of each job and turning off I/Os.
    <details>
    <summary>python mlfq.py -j 2 -n 2 -i 0 -s 26 -m 30 -M 0 -c</summary>
          
          Here is the list of inputs:
          OPTIONS jobs 2
          OPTIONS queues 2
          OPTIONS allotments for queue  1 is   1
          OPTIONS quantum length for queue  1 is  10
          OPTIONS allotments for queue  0 is   1
          OPTIONS quantum length for queue  0 is  10
          OPTIONS boost 0
          OPTIONS ioTime 0
          OPTIONS stayAfterIO False
          OPTIONS iobump False
          
          
          For each job, three defining characteristics are given:
            startTime : at what time does the job enter the system
            runTime   : the total CPU time needed by the job to finish
            ioFreq    : every ioFreq time units, the job issues an I/O
                        (the I/O takes ioTime units to complete)
          
          Job List:
            Job  0: startTime   0 - runTime  22 - ioFreq   0
            Job  1: startTime   0 - runTime   6 - ioFreq   0
          
          
          Execution Trace:
          
          [ time 0 ] JOB BEGINS by JOB 0
          [ time 0 ] JOB BEGINS by JOB 1
          [ time 0 ] Run JOB 0 at PRIORITY 1 [ TICKS 9 ALLOT 1 TIME 21 (of 22) ]
          [ time 1 ] Run JOB 0 at PRIORITY 1 [ TICKS 8 ALLOT 1 TIME 20 (of 22) ]
          [ time 2 ] Run JOB 0 at PRIORITY 1 [ TICKS 7 ALLOT 1 TIME 19 (of 22) ]
          [ time 3 ] Run JOB 0 at PRIORITY 1 [ TICKS 6 ALLOT 1 TIME 18 (of 22) ]
          [ time 4 ] Run JOB 0 at PRIORITY 1 [ TICKS 5 ALLOT 1 TIME 17 (of 22) ]
          [ time 5 ] Run JOB 0 at PRIORITY 1 [ TICKS 4 ALLOT 1 TIME 16 (of 22) ]
          [ time 6 ] Run JOB 0 at PRIORITY 1 [ TICKS 3 ALLOT 1 TIME 15 (of 22) ]
          [ time 7 ] Run JOB 0 at PRIORITY 1 [ TICKS 2 ALLOT 1 TIME 14 (of 22) ]
          [ time 8 ] Run JOB 0 at PRIORITY 1 [ TICKS 1 ALLOT 1 TIME 13 (of 22) ]
          [ time 9 ] Run JOB 0 at PRIORITY 1 [ TICKS 0 ALLOT 1 TIME 12 (of 22) ]
          [ time 10 ] Run JOB 1 at PRIORITY 1 [ TICKS 9 ALLOT 1 TIME 5 (of 6) ]
          [ time 11 ] Run JOB 1 at PRIORITY 1 [ TICKS 8 ALLOT 1 TIME 4 (of 6) ]
          [ time 12 ] Run JOB 1 at PRIORITY 1 [ TICKS 7 ALLOT 1 TIME 3 (of 6) ]
          [ time 13 ] Run JOB 1 at PRIORITY 1 [ TICKS 6 ALLOT 1 TIME 2 (of 6) ]
          [ time 14 ] Run JOB 1 at PRIORITY 1 [ TICKS 5 ALLOT 1 TIME 1 (of 6) ]
          [ time 15 ] Run JOB 1 at PRIORITY 1 [ TICKS 4 ALLOT 1 TIME 0 (of 6) ]
          [ time 16 ] FINISHED JOB 1
          [ time 16 ] Run JOB 0 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 11 (of 22) ]
          [ time 17 ] Run JOB 0 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 10 (of 22) ]
          [ time 18 ] Run JOB 0 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 9 (of 22) ]
          [ time 19 ] Run JOB 0 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 8 (of 22) ]
          [ time 20 ] Run JOB 0 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 7 (of 22) ]
          [ time 21 ] Run JOB 0 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 6 (of 22) ]
          [ time 22 ] Run JOB 0 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 5 (of 22) ]
          [ time 23 ] Run JOB 0 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 4 (of 22) ]
          [ time 24 ] Run JOB 0 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 3 (of 22) ]
          [ time 25 ] Run JOB 0 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 2 (of 22) ]
          [ time 26 ] Run JOB 0 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 1 (of 22) ]
          [ time 27 ] Run JOB 0 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 0 (of 22) ]
          [ time 28 ] FINISHED JOB 0
          
          Final statistics:
            Job  0: startTime   0 - response   0 - turnaround  28
            Job  1: startTime   0 - response  10 - turnaround  16
            Avg  1: startTime n/a - response 5.00 - turnaround 22.00
    </details>
    <details>
    <summary>python mlfq.py -j 2 -n 2 -i 0 -s 8 -m 30 -M 0 -c</summary>
       
          Here is the list of inputs:
          OPTIONS jobs 2
          OPTIONS queues 2
          OPTIONS allotments for queue  1 is   1
          OPTIONS quantum length for queue  1 is  10
          OPTIONS allotments for queue  0 is   1
          OPTIONS quantum length for queue  0 is  10
          OPTIONS boost 0
          OPTIONS ioTime 0
          OPTIONS stayAfterIO False
          OPTIONS iobump False
          
          
          For each job, three defining characteristics are given:
            startTime : at what time does the job enter the system
            runTime   : the total CPU time needed by the job to finish
            ioFreq    : every ioFreq time units, the job issues an I/O
                        (the I/O takes ioTime units to complete)
          
          Job List:
            Job  0: startTime   0 - runTime   7 - ioFreq   0
            Job  1: startTime   0 - runTime   4 - ioFreq   0
          
          
          Execution Trace:
          
          [ time 0 ] JOB BEGINS by JOB 0
          [ time 0 ] JOB BEGINS by JOB 1
          [ time 0 ] Run JOB 0 at PRIORITY 1 [ TICKS 9 ALLOT 1 TIME 6 (of 7) ]
          [ time 1 ] Run JOB 0 at PRIORITY 1 [ TICKS 8 ALLOT 1 TIME 5 (of 7) ]
          [ time 2 ] Run JOB 0 at PRIORITY 1 [ TICKS 7 ALLOT 1 TIME 4 (of 7) ]
          [ time 3 ] Run JOB 0 at PRIORITY 1 [ TICKS 6 ALLOT 1 TIME 3 (of 7) ]
          [ time 4 ] Run JOB 0 at PRIORITY 1 [ TICKS 5 ALLOT 1 TIME 2 (of 7) ]
          [ time 5 ] Run JOB 0 at PRIORITY 1 [ TICKS 4 ALLOT 1 TIME 1 (of 7) ]
          [ time 6 ] Run JOB 0 at PRIORITY 1 [ TICKS 3 ALLOT 1 TIME 0 (of 7) ]
          [ time 7 ] FINISHED JOB 0
          [ time 7 ] Run JOB 1 at PRIORITY 1 [ TICKS 9 ALLOT 1 TIME 3 (of 4) ]
          [ time 8 ] Run JOB 1 at PRIORITY 1 [ TICKS 8 ALLOT 1 TIME 2 (of 4) ]
          [ time 9 ] Run JOB 1 at PRIORITY 1 [ TICKS 7 ALLOT 1 TIME 1 (of 4) ]
          [ time 10 ] Run JOB 1 at PRIORITY 1 [ TICKS 6 ALLOT 1 TIME 0 (of 4) ]
          [ time 11 ] FINISHED JOB 1
          
          Final statistics:
            Job  0: startTime   0 - response   0 - turnaround   7
            Job  1: startTime   0 - response   7 - turnaround  11
            Avg  1: startTime n/a - response 3.50 - turnaround 9.00
    </details>
2.  How would you run the scheduler to reproduce each of the examples in the chapter?

    <details>
    <summary>Ejemplo 1: MLFQ de 3 colas, quantum de 10 segundos para cada cola y solo un proceso</summary>
    <details>
    <summary>python mlfq.py --jlist 0,50,0 -n 3 -q 10 -c</summary>

          Here is the list of inputs:
          OPTIONS jobs 1
          OPTIONS queues 3
          OPTIONS allotments for queue  2 is   1
          OPTIONS quantum length for queue  2 is  10
          OPTIONS allotments for queue  1 is   1
          OPTIONS quantum length for queue  1 is  10
          OPTIONS allotments for queue  0 is   1
          OPTIONS quantum length for queue  0 is  10
          OPTIONS boost 0
          OPTIONS ioTime 5
          OPTIONS stayAfterIO False
          OPTIONS iobump False


          For each job, three defining characteristics are given:
            startTime : at what time does the job enter the system
            runTime   : the total CPU time needed by the job to finish
            ioFreq    : every ioFreq time units, the job issues an I/O
                        (the I/O takes ioTime units to complete)

          Job List:
            Job  0: startTime   0 - runTime  50 - ioFreq   0


          Execution Trace:

          [ time 0 ] JOB BEGINS by JOB 0
          [ time 0 ] Run JOB 0 at PRIORITY 2 [ TICKS 9 ALLOT 1 TIME 49 (of 50) ]
          [ time 1 ] Run JOB 0 at PRIORITY 2 [ TICKS 8 ALLOT 1 TIME 48 (of 50) ]
          [ time 2 ] Run JOB 0 at PRIORITY 2 [ TICKS 7 ALLOT 1 TIME 47 (of 50) ]
          [ time 3 ] Run JOB 0 at PRIORITY 2 [ TICKS 6 ALLOT 1 TIME 46 (of 50) ]
          [ time 4 ] Run JOB 0 at PRIORITY 2 [ TICKS 5 ALLOT 1 TIME 45 (of 50) ]
          [ time 5 ] Run JOB 0 at PRIORITY 2 [ TICKS 4 ALLOT 1 TIME 44 (of 50) ]
          [ time 6 ] Run JOB 0 at PRIORITY 2 [ TICKS 3 ALLOT 1 TIME 43 (of 50) ]
          [ time 7 ] Run JOB 0 at PRIORITY 2 [ TICKS 2 ALLOT 1 TIME 42 (of 50) ]
          [ time 8 ] Run JOB 0 at PRIORITY 2 [ TICKS 1 ALLOT 1 TIME 41 (of 50) ]
          [ time 9 ] Run JOB 0 at PRIORITY 2 [ TICKS 0 ALLOT 1 TIME 40 (of 50) ]
          [ time 10 ] Run JOB 0 at PRIORITY 1 [ TICKS 9 ALLOT 1 TIME 39 (of 50) ]
          [ time 11 ] Run JOB 0 at PRIORITY 1 [ TICKS 8 ALLOT 1 TIME 38 (of 50) ]
          [ time 12 ] Run JOB 0 at PRIORITY 1 [ TICKS 7 ALLOT 1 TIME 37 (of 50) ]
          [ time 13 ] Run JOB 0 at PRIORITY 1 [ TICKS 6 ALLOT 1 TIME 36 (of 50) ]
          [ time 14 ] Run JOB 0 at PRIORITY 1 [ TICKS 5 ALLOT 1 TIME 35 (of 50) ]
          [ time 15 ] Run JOB 0 at PRIORITY 1 [ TICKS 4 ALLOT 1 TIME 34 (of 50) ]
          [ time 16 ] Run JOB 0 at PRIORITY 1 [ TICKS 3 ALLOT 1 TIME 33 (of 50) ]
          [ time 17 ] Run JOB 0 at PRIORITY 1 [ TICKS 2 ALLOT 1 TIME 32 (of 50) ]
          [ time 18 ] Run JOB 0 at PRIORITY 1 [ TICKS 1 ALLOT 1 TIME 31 (of 50) ]
          [ time 19 ] Run JOB 0 at PRIORITY 1 [ TICKS 0 ALLOT 1 TIME 30 (of 50) ]
          [ time 20 ] Run JOB 0 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 29 (of 50) ]
          [ time 21 ] Run JOB 0 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 28 (of 50) ]
          [ time 22 ] Run JOB 0 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 27 (of 50) ]
          [ time 23 ] Run JOB 0 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 26 (of 50) ]
          [ time 24 ] Run JOB 0 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 25 (of 50) ]
          [ time 25 ] Run JOB 0 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 24 (of 50) ]
          [ time 26 ] Run JOB 0 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 23 (of 50) ]
          [ time 27 ] Run JOB 0 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 22 (of 50) ]
          [ time 28 ] Run JOB 0 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 21 (of 50) ]
          [ time 29 ] Run JOB 0 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 20 (of 50) ]
          [ time 30 ] Run JOB 0 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 19 (of 50) ]
          [ time 31 ] Run JOB 0 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 18 (of 50) ]
          [ time 32 ] Run JOB 0 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 17 (of 50) ]
          [ time 33 ] Run JOB 0 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 16 (of 50) ]
          [ time 34 ] Run JOB 0 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 15 (of 50) ]
          [ time 35 ] Run JOB 0 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 14 (of 50) ]
          [ time 36 ] Run JOB 0 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 13 (of 50) ]
          [ time 37 ] Run JOB 0 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 12 (of 50) ]
          [ time 38 ] Run JOB 0 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 11 (of 50) ]
          [ time 39 ] Run JOB 0 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 10 (of 50) ]
          [ time 40 ] Run JOB 0 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 9 (of 50) ]
          [ time 41 ] Run JOB 0 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 8 (of 50) ]
          [ time 42 ] Run JOB 0 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 7 (of 50) ]
          [ time 43 ] Run JOB 0 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 6 (of 50) ]
          [ time 44 ] Run JOB 0 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 5 (of 50) ]
          [ time 45 ] Run JOB 0 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 4 (of 50) ]
          [ time 46 ] Run JOB 0 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 3 (of 50) ]
          [ time 47 ] Run JOB 0 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 2 (of 50) ]
          [ time 48 ] Run JOB 0 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 1 (of 50) ]
          [ time 49 ] Run JOB 0 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 0 (of 50) ]
          [ time 50 ] FINISHED JOB 0

          Final statistics:
            Job  0: startTime   0 - response   0 - turnaround  50

            Avg  0: startTime n/a - response 0.00 - turnaround 50.00

    </details>
    </details>
    <details>
    <summary>Ejemplo 2: MLFQ de 3 colas, quantum de 10 segundos para cada cola, proceso 1 CPU-bound, proceso 2 llega en t = 100, tiempo de ejecucion = 20 </summary>
    <details>
    <summary>python mlfq.py --jlist 0,200,0:100,20,0 -q 10 -n 3 -c</summary>
       
                Here is the list of inputs:
                OPTIONS jobs 2
                OPTIONS queues 3
                OPTIONS allotments for queue  2 is   1
                OPTIONS quantum length for queue  2 is  10
                OPTIONS allotments for queue  1 is   1
                OPTIONS quantum length for queue  1 is  10
                OPTIONS allotments for queue  0 is   1
                OPTIONS quantum length for queue  0 is  10
                OPTIONS boost 0
                OPTIONS ioTime 5
                OPTIONS stayAfterIO False
                OPTIONS iobump False
                
                
                For each job, three defining characteristics are given:
                  startTime : at what time does the job enter the system
                  runTime   : the total CPU time needed by the job to finish
                  ioFreq    : every ioFreq time units, the job issues an I/O
                              (the I/O takes ioTime units to complete)
                
                Job List:
                  Job  0: startTime   0 - runTime 200 - ioFreq   0
                  Job  1: startTime 100 - runTime  20 - ioFreq   0
                
                
                Execution Trace:
                
                [ time 0 ] JOB BEGINS by JOB 0
                [ time 0 ] Run JOB 0 at PRIORITY 2 [ TICKS 9 ALLOT 1 TIME 199 (of 200) ]
                [ time 1 ] Run JOB 0 at PRIORITY 2 [ TICKS 8 ALLOT 1 TIME 198 (of 200) ]
                [ time 2 ] Run JOB 0 at PRIORITY 2 [ TICKS 7 ALLOT 1 TIME 197 (of 200) ]
                [ time 3 ] Run JOB 0 at PRIORITY 2 [ TICKS 6 ALLOT 1 TIME 196 (of 200) ]
                [ time 4 ] Run JOB 0 at PRIORITY 2 [ TICKS 5 ALLOT 1 TIME 195 (of 200) ]
                [ time 5 ] Run JOB 0 at PRIORITY 2 [ TICKS 4 ALLOT 1 TIME 194 (of 200) ]
                [ time 6 ] Run JOB 0 at PRIORITY 2 [ TICKS 3 ALLOT 1 TIME 193 (of 200) ]
                [ time 7 ] Run JOB 0 at PRIORITY 2 [ TICKS 2 ALLOT 1 TIME 192 (of 200) ]
                [ time 8 ] Run JOB 0 at PRIORITY 2 [ TICKS 1 ALLOT 1 TIME 191 (of 200) ]
                [ time 9 ] Run JOB 0 at PRIORITY 2 [ TICKS 0 ALLOT 1 TIME 190 (of 200) ]
                [ time 10 ] Run JOB 0 at PRIORITY 1 [ TICKS 9 ALLOT 1 TIME 189 (of 200) ]
                [ time 11 ] Run JOB 0 at PRIORITY 1 [ TICKS 8 ALLOT 1 TIME 188 (of 200) ]
                [ time 12 ] Run JOB 0 at PRIORITY 1 [ TICKS 7 ALLOT 1 TIME 187 (of 200) ]
                [ time 13 ] Run JOB 0 at PRIORITY 1 [ TICKS 6 ALLOT 1 TIME 186 (of 200) ]
                [ time 14 ] Run JOB 0 at PRIORITY 1 [ TICKS 5 ALLOT 1 TIME 185 (of 200) ]
                [ time 15 ] Run JOB 0 at PRIORITY 1 [ TICKS 4 ALLOT 1 TIME 184 (of 200) ]
                [ time 16 ] Run JOB 0 at PRIORITY 1 [ TICKS 3 ALLOT 1 TIME 183 (of 200) ]
                [ time 17 ] Run JOB 0 at PRIORITY 1 [ TICKS 2 ALLOT 1 TIME 182 (of 200) ]
                [ time 18 ] Run JOB 0 at PRIORITY 1 [ TICKS 1 ALLOT 1 TIME 181 (of 200) ]
                [ time 19 ] Run JOB 0 at PRIORITY 1 [ TICKS 0 ALLOT 1 TIME 180 (of 200) ]
                [ time 20 ] Run JOB 0 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 179 (of 200) ]
                [ time 21 ] Run JOB 0 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 178 (of 200) ]
                [ time 22 ] Run JOB 0 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 177 (of 200) ]
                [ time 23 ] Run JOB 0 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 176 (of 200) ]
                [ time 24 ] Run JOB 0 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 175 (of 200) ]
                [ time 25 ] Run JOB 0 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 174 (of 200) ]
                [ time 26 ] Run JOB 0 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 173 (of 200) ]
                [ time 27 ] Run JOB 0 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 172 (of 200) ]
                [ time 28 ] Run JOB 0 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 171 (of 200) ]
                [ time 29 ] Run JOB 0 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 170 (of 200) ]
                [ time 30 ] Run JOB 0 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 169 (of 200) ]
                [ time 31 ] Run JOB 0 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 168 (of 200) ]
                [ time 32 ] Run JOB 0 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 167 (of 200) ]
                [ time 33 ] Run JOB 0 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 166 (of 200) ]
                [ time 34 ] Run JOB 0 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 165 (of 200) ]
                [ time 35 ] Run JOB 0 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 164 (of 200) ]
                [ time 36 ] Run JOB 0 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 163 (of 200) ]
                [ time 37 ] Run JOB 0 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 162 (of 200) ]
                [ time 38 ] Run JOB 0 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 161 (of 200) ]
                [ time 39 ] Run JOB 0 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 160 (of 200) ]
                [ time 40 ] Run JOB 0 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 159 (of 200) ]
                [ time 41 ] Run JOB 0 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 158 (of 200) ]
                [ time 42 ] Run JOB 0 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 157 (of 200) ]
                [ time 43 ] Run JOB 0 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 156 (of 200) ]
                [ time 44 ] Run JOB 0 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 155 (of 200) ]
                [ time 45 ] Run JOB 0 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 154 (of 200) ]
                [ time 46 ] Run JOB 0 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 153 (of 200) ]
                [ time 47 ] Run JOB 0 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 152 (of 200) ]
                [ time 48 ] Run JOB 0 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 151 (of 200) ]
                [ time 49 ] Run JOB 0 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 150 (of 200) ]
                [ time 50 ] Run JOB 0 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 149 (of 200) ]
                [ time 51 ] Run JOB 0 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 148 (of 200) ]
                [ time 52 ] Run JOB 0 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 147 (of 200) ]
                [ time 53 ] Run JOB 0 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 146 (of 200) ]
                [ time 54 ] Run JOB 0 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 145 (of 200) ]
                [ time 55 ] Run JOB 0 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 144 (of 200) ]
                [ time 56 ] Run JOB 0 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 143 (of 200) ]
                [ time 57 ] Run JOB 0 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 142 (of 200) ]
                [ time 58 ] Run JOB 0 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 141 (of 200) ]
                [ time 59 ] Run JOB 0 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 140 (of 200) ]
                [ time 60 ] Run JOB 0 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 139 (of 200) ]
                [ time 61 ] Run JOB 0 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 138 (of 200) ]
                [ time 62 ] Run JOB 0 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 137 (of 200) ]
                [ time 63 ] Run JOB 0 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 136 (of 200) ]
                [ time 64 ] Run JOB 0 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 135 (of 200) ]
                [ time 65 ] Run JOB 0 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 134 (of 200) ]
                [ time 66 ] Run JOB 0 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 133 (of 200) ]
                [ time 67 ] Run JOB 0 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 132 (of 200) ]
                [ time 68 ] Run JOB 0 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 131 (of 200) ]
                [ time 69 ] Run JOB 0 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 130 (of 200) ]
                [ time 70 ] Run JOB 0 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 129 (of 200) ]
                [ time 71 ] Run JOB 0 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 128 (of 200) ]
                [ time 72 ] Run JOB 0 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 127 (of 200) ]
                [ time 73 ] Run JOB 0 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 126 (of 200) ]
                [ time 74 ] Run JOB 0 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 125 (of 200) ]
                [ time 75 ] Run JOB 0 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 124 (of 200) ]
                [ time 76 ] Run JOB 0 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 123 (of 200) ]
                [ time 77 ] Run JOB 0 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 122 (of 200) ]
                [ time 78 ] Run JOB 0 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 121 (of 200) ]
                [ time 79 ] Run JOB 0 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 120 (of 200) ]
                [ time 80 ] Run JOB 0 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 119 (of 200) ]
                [ time 81 ] Run JOB 0 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 118 (of 200) ]
                [ time 82 ] Run JOB 0 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 117 (of 200) ]
                [ time 83 ] Run JOB 0 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 116 (of 200) ]
                [ time 84 ] Run JOB 0 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 115 (of 200) ]
                [ time 85 ] Run JOB 0 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 114 (of 200) ]
                [ time 86 ] Run JOB 0 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 113 (of 200) ]
                [ time 87 ] Run JOB 0 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 112 (of 200) ]
                [ time 88 ] Run JOB 0 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 111 (of 200) ]
                [ time 89 ] Run JOB 0 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 110 (of 200) ]
                [ time 90 ] Run JOB 0 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 109 (of 200) ]
                [ time 91 ] Run JOB 0 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 108 (of 200) ]
                [ time 92 ] Run JOB 0 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 107 (of 200) ]
                [ time 93 ] Run JOB 0 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 106 (of 200) ]
                [ time 94 ] Run JOB 0 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 105 (of 200) ]
                [ time 95 ] Run JOB 0 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 104 (of 200) ]
                [ time 96 ] Run JOB 0 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 103 (of 200) ]
                [ time 97 ] Run JOB 0 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 102 (of 200) ]
                [ time 98 ] Run JOB 0 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 101 (of 200) ]
                [ time 99 ] Run JOB 0 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 100 (of 200) ]
                [ time 100 ] JOB BEGINS by JOB 1
                [ time 100 ] Run JOB 1 at PRIORITY 2 [ TICKS 9 ALLOT 1 TIME 19 (of 20) ]
                [ time 101 ] Run JOB 1 at PRIORITY 2 [ TICKS 8 ALLOT 1 TIME 18 (of 20) ]
                [ time 102 ] Run JOB 1 at PRIORITY 2 [ TICKS 7 ALLOT 1 TIME 17 (of 20) ]
                [ time 103 ] Run JOB 1 at PRIORITY 2 [ TICKS 6 ALLOT 1 TIME 16 (of 20) ]
                [ time 104 ] Run JOB 1 at PRIORITY 2 [ TICKS 5 ALLOT 1 TIME 15 (of 20) ]
                [ time 105 ] Run JOB 1 at PRIORITY 2 [ TICKS 4 ALLOT 1 TIME 14 (of 20) ]
                [ time 106 ] Run JOB 1 at PRIORITY 2 [ TICKS 3 ALLOT 1 TIME 13 (of 20) ]
                [ time 107 ] Run JOB 1 at PRIORITY 2 [ TICKS 2 ALLOT 1 TIME 12 (of 20) ]
                [ time 108 ] Run JOB 1 at PRIORITY 2 [ TICKS 1 ALLOT 1 TIME 11 (of 20) ]
                [ time 109 ] Run JOB 1 at PRIORITY 2 [ TICKS 0 ALLOT 1 TIME 10 (of 20) ]
                [ time 110 ] Run JOB 1 at PRIORITY 1 [ TICKS 9 ALLOT 1 TIME 9 (of 20) ]
                [ time 111 ] Run JOB 1 at PRIORITY 1 [ TICKS 8 ALLOT 1 TIME 8 (of 20) ]
                [ time 112 ] Run JOB 1 at PRIORITY 1 [ TICKS 7 ALLOT 1 TIME 7 (of 20) ]
                [ time 113 ] Run JOB 1 at PRIORITY 1 [ TICKS 6 ALLOT 1 TIME 6 (of 20) ]
                [ time 114 ] Run JOB 1 at PRIORITY 1 [ TICKS 5 ALLOT 1 TIME 5 (of 20) ]
                [ time 115 ] Run JOB 1 at PRIORITY 1 [ TICKS 4 ALLOT 1 TIME 4 (of 20) ]
                [ time 116 ] Run JOB 1 at PRIORITY 1 [ TICKS 3 ALLOT 1 TIME 3 (of 20) ]
                [ time 117 ] Run JOB 1 at PRIORITY 1 [ TICKS 2 ALLOT 1 TIME 2 (of 20) ]
                [ time 118 ] Run JOB 1 at PRIORITY 1 [ TICKS 1 ALLOT 1 TIME 1 (of 20) ]
                [ time 119 ] Run JOB 1 at PRIORITY 1 [ TICKS 0 ALLOT 1 TIME 0 (of 20) ]
                [ time 120 ] FINISHED JOB 1
                [ time 120 ] Run JOB 0 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 99 (of 200) ]
                [ time 121 ] Run JOB 0 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 98 (of 200) ]
                [ time 122 ] Run JOB 0 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 97 (of 200) ]
                [ time 123 ] Run JOB 0 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 96 (of 200) ]
                [ time 124 ] Run JOB 0 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 95 (of 200) ]
                [ time 125 ] Run JOB 0 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 94 (of 200) ]
                [ time 126 ] Run JOB 0 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 93 (of 200) ]
                [ time 127 ] Run JOB 0 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 92 (of 200) ]
                [ time 128 ] Run JOB 0 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 91 (of 200) ]
                [ time 129 ] Run JOB 0 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 90 (of 200) ]
                [ time 130 ] Run JOB 0 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 89 (of 200) ]
                [ time 131 ] Run JOB 0 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 88 (of 200) ]
                [ time 132 ] Run JOB 0 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 87 (of 200) ]
                [ time 133 ] Run JOB 0 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 86 (of 200) ]
                [ time 134 ] Run JOB 0 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 85 (of 200) ]
                [ time 135 ] Run JOB 0 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 84 (of 200) ]
                [ time 136 ] Run JOB 0 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 83 (of 200) ]
                [ time 137 ] Run JOB 0 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 82 (of 200) ]
                [ time 138 ] Run JOB 0 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 81 (of 200) ]
                [ time 139 ] Run JOB 0 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 80 (of 200) ]
                [ time 140 ] Run JOB 0 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 79 (of 200) ]
                [ time 141 ] Run JOB 0 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 78 (of 200) ]
                [ time 142 ] Run JOB 0 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 77 (of 200) ]
                [ time 143 ] Run JOB 0 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 76 (of 200) ]
                [ time 144 ] Run JOB 0 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 75 (of 200) ]
                [ time 145 ] Run JOB 0 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 74 (of 200) ]
                [ time 146 ] Run JOB 0 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 73 (of 200) ]
                [ time 147 ] Run JOB 0 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 72 (of 200) ]
                [ time 148 ] Run JOB 0 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 71 (of 200) ]
                [ time 149 ] Run JOB 0 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 70 (of 200) ]
                [ time 150 ] Run JOB 0 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 69 (of 200) ]
                [ time 151 ] Run JOB 0 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 68 (of 200) ]
                [ time 152 ] Run JOB 0 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 67 (of 200) ]
                [ time 153 ] Run JOB 0 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 66 (of 200) ]
                [ time 154 ] Run JOB 0 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 65 (of 200) ]
                [ time 155 ] Run JOB 0 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 64 (of 200) ]
                [ time 156 ] Run JOB 0 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 63 (of 200) ]
                [ time 157 ] Run JOB 0 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 62 (of 200) ]
                [ time 158 ] Run JOB 0 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 61 (of 200) ]
                [ time 159 ] Run JOB 0 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 60 (of 200) ]
                [ time 160 ] Run JOB 0 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 59 (of 200) ]
                [ time 161 ] Run JOB 0 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 58 (of 200) ]
                [ time 162 ] Run JOB 0 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 57 (of 200) ]
                [ time 163 ] Run JOB 0 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 56 (of 200) ]
                [ time 164 ] Run JOB 0 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 55 (of 200) ]
                [ time 165 ] Run JOB 0 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 54 (of 200) ]
                [ time 166 ] Run JOB 0 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 53 (of 200) ]
                [ time 167 ] Run JOB 0 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 52 (of 200) ]
                [ time 168 ] Run JOB 0 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 51 (of 200) ]
                [ time 169 ] Run JOB 0 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 50 (of 200) ]
                [ time 170 ] Run JOB 0 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 49 (of 200) ]
                [ time 171 ] Run JOB 0 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 48 (of 200) ]
                [ time 172 ] Run JOB 0 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 47 (of 200) ]
                [ time 173 ] Run JOB 0 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 46 (of 200) ]
                [ time 174 ] Run JOB 0 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 45 (of 200) ]
                [ time 175 ] Run JOB 0 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 44 (of 200) ]
                [ time 176 ] Run JOB 0 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 43 (of 200) ]
                [ time 177 ] Run JOB 0 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 42 (of 200) ]
                [ time 178 ] Run JOB 0 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 41 (of 200) ]
                [ time 179 ] Run JOB 0 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 40 (of 200) ]
                [ time 180 ] Run JOB 0 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 39 (of 200) ]
                [ time 181 ] Run JOB 0 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 38 (of 200) ]
                [ time 182 ] Run JOB 0 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 37 (of 200) ]
                [ time 183 ] Run JOB 0 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 36 (of 200) ]
                [ time 184 ] Run JOB 0 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 35 (of 200) ]
                [ time 185 ] Run JOB 0 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 34 (of 200) ]
                [ time 186 ] Run JOB 0 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 33 (of 200) ]
                [ time 187 ] Run JOB 0 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 32 (of 200) ]
                [ time 188 ] Run JOB 0 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 31 (of 200) ]
                [ time 189 ] Run JOB 0 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 30 (of 200) ]
                [ time 190 ] Run JOB 0 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 29 (of 200) ]
                [ time 191 ] Run JOB 0 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 28 (of 200) ]
                [ time 192 ] Run JOB 0 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 27 (of 200) ]
                [ time 193 ] Run JOB 0 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 26 (of 200) ]
                [ time 194 ] Run JOB 0 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 25 (of 200) ]
                [ time 195 ] Run JOB 0 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 24 (of 200) ]
                [ time 196 ] Run JOB 0 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 23 (of 200) ]
                [ time 197 ] Run JOB 0 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 22 (of 200) ]
                [ time 198 ] Run JOB 0 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 21 (of 200) ]
                [ time 199 ] Run JOB 0 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 20 (of 200) ]
                [ time 200 ] Run JOB 0 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 19 (of 200) ]
                [ time 201 ] Run JOB 0 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 18 (of 200) ]
                [ time 202 ] Run JOB 0 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 17 (of 200) ]
                [ time 203 ] Run JOB 0 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 16 (of 200) ]
                [ time 204 ] Run JOB 0 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 15 (of 200) ]
                [ time 205 ] Run JOB 0 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 14 (of 200) ]
                [ time 206 ] Run JOB 0 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 13 (of 200) ]
                [ time 207 ] Run JOB 0 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 12 (of 200) ]
                [ time 208 ] Run JOB 0 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 11 (of 200) ]
                [ time 209 ] Run JOB 0 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 10 (of 200) ]
                [ time 210 ] Run JOB 0 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 9 (of 200) ]
                [ time 211 ] Run JOB 0 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 8 (of 200) ]
                [ time 212 ] Run JOB 0 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 7 (of 200) ]
                [ time 213 ] Run JOB 0 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 6 (of 200) ]
                [ time 214 ] Run JOB 0 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 5 (of 200) ]
                [ time 215 ] Run JOB 0 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 4 (of 200) ]
                [ time 216 ] Run JOB 0 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 3 (of 200) ]
                [ time 217 ] Run JOB 0 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 2 (of 200) ]
                [ time 218 ] Run JOB 0 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 1 (of 200) ]
                [ time 219 ] Run JOB 0 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 0 (of 200) ]
                [ time 220 ] FINISHED JOB 0
                
                Final statistics:
                  Job  0: startTime   0 - response   0 - turnaround 220
                  Job  1: startTime 100 - response   0 - turnaround  20
                
                  Avg  1: startTime n/a - response 0.00 - turnaround 120.00
    </details>
    </details>

    <details>
    <summary>Ejemplo 3: MLFQ de 3 colas, quantum de 10 segundos para cada cola, proceso 1 CPU-bound, proceso 2 llega en t = 50, I/O bound, usa la CPU 1ms y realiza una operacion de I/O </summary>
    <details>
    <summary>python mlfq.py --jlist 0,178,0:50,22,1 -q 10 -n 3 -S -c</summary>

          Here is the list of inputs:
          OPTIONS jobs 2
          OPTIONS queues 3
          OPTIONS allotments for queue  2 is   1
          OPTIONS quantum length for queue  2 is  10
          OPTIONS allotments for queue  1 is   1
          OPTIONS quantum length for queue  1 is  10
          OPTIONS allotments for queue  0 is   1
          OPTIONS quantum length for queue  0 is  10
          OPTIONS boost 0
          OPTIONS ioTime 5
          OPTIONS stayAfterIO True
          OPTIONS iobump False


          For each job, three defining characteristics are given:
            startTime : at what time does the job enter the system
            runTime   : the total CPU time needed by the job to finish
            ioFreq    : every ioFreq time units, the job issues an I/O
                        (the I/O takes ioTime units to complete)

          Job List:
            Job  0: startTime   0 - runTime 178 - ioFreq   0
            Job  1: startTime  50 - runTime  22 - ioFreq   1


          Execution Trace:

          [ time 0 ] JOB BEGINS by JOB 0
          [ time 0 ] Run JOB 0 at PRIORITY 2 [ TICKS 9 ALLOT 1 TIME 177 (of 178) ]
          [ time 1 ] Run JOB 0 at PRIORITY 2 [ TICKS 8 ALLOT 1 TIME 176 (of 178) ]
          [ time 2 ] Run JOB 0 at PRIORITY 2 [ TICKS 7 ALLOT 1 TIME 175 (of 178) ]
          [ time 3 ] Run JOB 0 at PRIORITY 2 [ TICKS 6 ALLOT 1 TIME 174 (of 178) ]
          [ time 4 ] Run JOB 0 at PRIORITY 2 [ TICKS 5 ALLOT 1 TIME 173 (of 178) ]
          [ time 5 ] Run JOB 0 at PRIORITY 2 [ TICKS 4 ALLOT 1 TIME 172 (of 178) ]
          [ time 6 ] Run JOB 0 at PRIORITY 2 [ TICKS 3 ALLOT 1 TIME 171 (of 178) ]
          [ time 7 ] Run JOB 0 at PRIORITY 2 [ TICKS 2 ALLOT 1 TIME 170 (of 178) ]
          [ time 8 ] Run JOB 0 at PRIORITY 2 [ TICKS 1 ALLOT 1 TIME 169 (of 178) ]
          [ time 9 ] Run JOB 0 at PRIORITY 2 [ TICKS 0 ALLOT 1 TIME 168 (of 178) ]
          [ time 10 ] Run JOB 0 at PRIORITY 1 [ TICKS 9 ALLOT 1 TIME 167 (of 178) ]
          [ time 11 ] Run JOB 0 at PRIORITY 1 [ TICKS 8 ALLOT 1 TIME 166 (of 178) ]
          [ time 12 ] Run JOB 0 at PRIORITY 1 [ TICKS 7 ALLOT 1 TIME 165 (of 178) ]
          [ time 13 ] Run JOB 0 at PRIORITY 1 [ TICKS 6 ALLOT 1 TIME 164 (of 178) ]
          [ time 14 ] Run JOB 0 at PRIORITY 1 [ TICKS 5 ALLOT 1 TIME 163 (of 178) ]
          [ time 15 ] Run JOB 0 at PRIORITY 1 [ TICKS 4 ALLOT 1 TIME 162 (of 178) ]
          [ time 16 ] Run JOB 0 at PRIORITY 1 [ TICKS 3 ALLOT 1 TIME 161 (of 178) ]
          [ time 17 ] Run JOB 0 at PRIORITY 1 [ TICKS 2 ALLOT 1 TIME 160 (of 178) ]
          [ time 18 ] Run JOB 0 at PRIORITY 1 [ TICKS 1 ALLOT 1 TIME 159 (of 178) ]
          [ time 19 ] Run JOB 0 at PRIORITY 1 [ TICKS 0 ALLOT 1 TIME 158 (of 178) ]
          [ time 20 ] Run JOB 0 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 157 (of 178) ]
          [ time 21 ] Run JOB 0 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 156 (of 178) ]
          [ time 22 ] Run JOB 0 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 155 (of 178) ]
          [ time 23 ] Run JOB 0 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 154 (of 178) ]
          [ time 24 ] Run JOB 0 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 153 (of 178) ]
          [ time 25 ] Run JOB 0 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 152 (of 178) ]
          [ time 26 ] Run JOB 0 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 151 (of 178) ]
          [ time 27 ] Run JOB 0 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 150 (of 178) ]
          [ time 28 ] Run JOB 0 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 149 (of 178) ]
          [ time 29 ] Run JOB 0 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 148 (of 178) ]
          [ time 30 ] Run JOB 0 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 147 (of 178) ]
          [ time 31 ] Run JOB 0 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 146 (of 178) ]
          [ time 32 ] Run JOB 0 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 145 (of 178) ]
          [ time 33 ] Run JOB 0 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 144 (of 178) ]
          [ time 34 ] Run JOB 0 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 143 (of 178) ]
          [ time 35 ] Run JOB 0 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 142 (of 178) ]
          [ time 36 ] Run JOB 0 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 141 (of 178) ]
          [ time 37 ] Run JOB 0 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 140 (of 178) ]
          [ time 38 ] Run JOB 0 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 139 (of 178) ]
          [ time 39 ] Run JOB 0 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 138 (of 178) ]
          [ time 40 ] Run JOB 0 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 137 (of 178) ]
          [ time 41 ] Run JOB 0 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 136 (of 178) ]
          [ time 42 ] Run JOB 0 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 135 (of 178) ]
          [ time 43 ] Run JOB 0 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 134 (of 178) ]
          [ time 44 ] Run JOB 0 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 133 (of 178) ]
          [ time 45 ] Run JOB 0 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 132 (of 178) ]
          [ time 46 ] Run JOB 0 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 131 (of 178) ]
          [ time 47 ] Run JOB 0 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 130 (of 178) ]
          [ time 48 ] Run JOB 0 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 129 (of 178) ]
          [ time 49 ] Run JOB 0 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 128 (of 178) ]
          [ time 50 ] JOB BEGINS by JOB 1
          [ time 50 ] Run JOB 1 at PRIORITY 2 [ TICKS 9 ALLOT 1 TIME 21 (of 22) ]
          [ time 51 ] IO_START by JOB 1
          IO DONE
          [ time 51 ] Run JOB 0 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 127 (of 178) ]
          [ time 52 ] Run JOB 0 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 126 (of 178) ]
          [ time 53 ] Run JOB 0 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 125 (of 178) ]
          [ time 54 ] Run JOB 0 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 124 (of 178) ]
          [ time 55 ] Run JOB 0 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 123 (of 178) ]
          [ time 56 ] IO_DONE by JOB 1
          [ time 56 ] Run JOB 1 at PRIORITY 2 [ TICKS 9 ALLOT 1 TIME 20 (of 22) ]
          [ time 57 ] IO_START by JOB 1
          IO DONE
          [ time 57 ] Run JOB 0 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 122 (of 178) ]
          [ time 58 ] Run JOB 0 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 121 (of 178) ]
          [ time 59 ] Run JOB 0 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 120 (of 178) ]
          [ time 60 ] Run JOB 0 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 119 (of 178) ]
          [ time 61 ] Run JOB 0 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 118 (of 178) ]
          [ time 62 ] IO_DONE by JOB 1
          [ time 62 ] Run JOB 1 at PRIORITY 2 [ TICKS 9 ALLOT 1 TIME 19 (of 22) ]
          [ time 63 ] IO_START by JOB 1
          IO DONE
          [ time 63 ] Run JOB 0 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 117 (of 178) ]
          [ time 64 ] Run JOB 0 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 116 (of 178) ]
          [ time 65 ] Run JOB 0 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 115 (of 178) ]
          [ time 66 ] Run JOB 0 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 114 (of 178) ]
          [ time 67 ] Run JOB 0 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 113 (of 178) ]
          [ time 68 ] IO_DONE by JOB 1
          [ time 68 ] Run JOB 1 at PRIORITY 2 [ TICKS 9 ALLOT 1 TIME 18 (of 22) ]
          [ time 69 ] IO_START by JOB 1
          IO DONE
          [ time 69 ] Run JOB 0 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 112 (of 178) ]
          [ time 70 ] Run JOB 0 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 111 (of 178) ]
          [ time 71 ] Run JOB 0 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 110 (of 178) ]
          [ time 72 ] Run JOB 0 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 109 (of 178) ]
          [ time 73 ] Run JOB 0 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 108 (of 178) ]
          [ time 74 ] IO_DONE by JOB 1
          [ time 74 ] Run JOB 1 at PRIORITY 2 [ TICKS 9 ALLOT 1 TIME 17 (of 22) ]
          [ time 75 ] IO_START by JOB 1
          IO DONE
          [ time 75 ] Run JOB 0 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 107 (of 178) ]
          [ time 76 ] Run JOB 0 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 106 (of 178) ]
          [ time 77 ] Run JOB 0 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 105 (of 178) ]
          [ time 78 ] Run JOB 0 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 104 (of 178) ]
          [ time 79 ] Run JOB 0 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 103 (of 178) ]
          [ time 80 ] IO_DONE by JOB 1
          [ time 80 ] Run JOB 1 at PRIORITY 2 [ TICKS 9 ALLOT 1 TIME 16 (of 22) ]
          [ time 81 ] IO_START by JOB 1
          IO DONE
          [ time 81 ] Run JOB 0 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 102 (of 178) ]
          [ time 82 ] Run JOB 0 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 101 (of 178) ]
          [ time 83 ] Run JOB 0 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 100 (of 178) ]
          [ time 84 ] Run JOB 0 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 99 (of 178) ]
          [ time 85 ] Run JOB 0 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 98 (of 178) ]
          [ time 86 ] IO_DONE by JOB 1
          [ time 86 ] Run JOB 1 at PRIORITY 2 [ TICKS 9 ALLOT 1 TIME 15 (of 22) ]
          [ time 87 ] IO_START by JOB 1
          IO DONE
          [ time 87 ] Run JOB 0 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 97 (of 178) ]
          [ time 88 ] Run JOB 0 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 96 (of 178) ]
          [ time 89 ] Run JOB 0 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 95 (of 178) ]
          [ time 90 ] Run JOB 0 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 94 (of 178) ]
          [ time 91 ] Run JOB 0 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 93 (of 178) ]
          [ time 92 ] IO_DONE by JOB 1
          [ time 92 ] Run JOB 1 at PRIORITY 2 [ TICKS 9 ALLOT 1 TIME 14 (of 22) ]
          [ time 93 ] IO_START by JOB 1
          IO DONE
          [ time 93 ] Run JOB 0 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 92 (of 178) ]
          [ time 94 ] Run JOB 0 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 91 (of 178) ]
          [ time 95 ] Run JOB 0 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 90 (of 178) ]
          [ time 96 ] Run JOB 0 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 89 (of 178) ]
          [ time 97 ] Run JOB 0 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 88 (of 178) ]
          [ time 98 ] IO_DONE by JOB 1
          [ time 98 ] Run JOB 1 at PRIORITY 2 [ TICKS 9 ALLOT 1 TIME 13 (of 22) ]
          [ time 99 ] IO_START by JOB 1
          IO DONE
          [ time 99 ] Run JOB 0 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 87 (of 178) ]
          [ time 100 ] Run JOB 0 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 86 (of 178) ]
          [ time 101 ] Run JOB 0 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 85 (of 178) ]
          [ time 102 ] Run JOB 0 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 84 (of 178) ]
          [ time 103 ] Run JOB 0 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 83 (of 178) ]
          [ time 104 ] IO_DONE by JOB 1
          [ time 104 ] Run JOB 1 at PRIORITY 2 [ TICKS 9 ALLOT 1 TIME 12 (of 22) ]
          [ time 105 ] IO_START by JOB 1
          IO DONE
          [ time 105 ] Run JOB 0 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 82 (of 178) ]
          [ time 106 ] Run JOB 0 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 81 (of 178) ]
          [ time 107 ] Run JOB 0 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 80 (of 178) ]
          [ time 108 ] Run JOB 0 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 79 (of 178) ]
          [ time 109 ] Run JOB 0 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 78 (of 178) ]
          [ time 110 ] IO_DONE by JOB 1
          [ time 110 ] Run JOB 1 at PRIORITY 2 [ TICKS 9 ALLOT 1 TIME 11 (of 22) ]
          [ time 111 ] IO_START by JOB 1
          IO DONE
          [ time 111 ] Run JOB 0 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 77 (of 178) ]
          [ time 112 ] Run JOB 0 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 76 (of 178) ]
          [ time 113 ] Run JOB 0 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 75 (of 178) ]
          [ time 114 ] Run JOB 0 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 74 (of 178) ]
          [ time 115 ] Run JOB 0 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 73 (of 178) ]
          [ time 116 ] IO_DONE by JOB 1
          [ time 116 ] Run JOB 1 at PRIORITY 2 [ TICKS 9 ALLOT 1 TIME 10 (of 22) ]
          [ time 117 ] IO_START by JOB 1
          IO DONE
          [ time 117 ] Run JOB 0 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 72 (of 178) ]
          [ time 118 ] Run JOB 0 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 71 (of 178) ]
          [ time 119 ] Run JOB 0 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 70 (of 178) ]
          [ time 120 ] Run JOB 0 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 69 (of 178) ]
          [ time 121 ] Run JOB 0 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 68 (of 178) ]
          [ time 122 ] IO_DONE by JOB 1
          [ time 122 ] Run JOB 1 at PRIORITY 2 [ TICKS 9 ALLOT 1 TIME 9 (of 22) ]
          [ time 123 ] IO_START by JOB 1
          IO DONE
          [ time 123 ] Run JOB 0 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 67 (of 178) ]
          [ time 124 ] Run JOB 0 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 66 (of 178) ]
          [ time 125 ] Run JOB 0 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 65 (of 178) ]
          [ time 126 ] Run JOB 0 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 64 (of 178) ]
          [ time 127 ] Run JOB 0 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 63 (of 178) ]
          [ time 128 ] IO_DONE by JOB 1
          [ time 128 ] Run JOB 1 at PRIORITY 2 [ TICKS 9 ALLOT 1 TIME 8 (of 22) ]
          [ time 129 ] IO_START by JOB 1
          IO DONE
          [ time 129 ] Run JOB 0 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 62 (of 178) ]
          [ time 130 ] Run JOB 0 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 61 (of 178) ]
          [ time 131 ] Run JOB 0 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 60 (of 178) ]
          [ time 132 ] Run JOB 0 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 59 (of 178) ]
          [ time 133 ] Run JOB 0 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 58 (of 178) ]
          [ time 134 ] IO_DONE by JOB 1
          [ time 134 ] Run JOB 1 at PRIORITY 2 [ TICKS 9 ALLOT 1 TIME 7 (of 22) ]
          [ time 135 ] IO_START by JOB 1
          IO DONE
          [ time 135 ] Run JOB 0 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 57 (of 178) ]
          [ time 136 ] Run JOB 0 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 56 (of 178) ]
          [ time 137 ] Run JOB 0 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 55 (of 178) ]
          [ time 138 ] Run JOB 0 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 54 (of 178) ]
          [ time 139 ] Run JOB 0 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 53 (of 178) ]
          [ time 140 ] IO_DONE by JOB 1
          [ time 140 ] Run JOB 1 at PRIORITY 2 [ TICKS 9 ALLOT 1 TIME 6 (of 22) ]
          [ time 141 ] IO_START by JOB 1
          IO DONE
          [ time 141 ] Run JOB 0 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 52 (of 178) ]
          [ time 142 ] Run JOB 0 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 51 (of 178) ]
          [ time 143 ] Run JOB 0 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 50 (of 178) ]
          [ time 144 ] Run JOB 0 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 49 (of 178) ]
          [ time 145 ] Run JOB 0 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 48 (of 178) ]
          [ time 146 ] IO_DONE by JOB 1
          [ time 146 ] Run JOB 1 at PRIORITY 2 [ TICKS 9 ALLOT 1 TIME 5 (of 22) ]
          [ time 147 ] IO_START by JOB 1
          IO DONE
          [ time 147 ] Run JOB 0 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 47 (of 178) ]
          [ time 148 ] Run JOB 0 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 46 (of 178) ]
          [ time 149 ] Run JOB 0 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 45 (of 178) ]
          [ time 150 ] Run JOB 0 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 44 (of 178) ]
          [ time 151 ] Run JOB 0 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 43 (of 178) ]
          [ time 152 ] IO_DONE by JOB 1
          [ time 152 ] Run JOB 1 at PRIORITY 2 [ TICKS 9 ALLOT 1 TIME 4 (of 22) ]
          [ time 153 ] IO_START by JOB 1
          IO DONE
          [ time 153 ] Run JOB 0 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 42 (of 178) ]
          [ time 154 ] Run JOB 0 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 41 (of 178) ]
          [ time 155 ] Run JOB 0 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 40 (of 178) ]
          [ time 156 ] Run JOB 0 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 39 (of 178) ]
          [ time 157 ] Run JOB 0 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 38 (of 178) ]
          [ time 158 ] IO_DONE by JOB 1
          [ time 158 ] Run JOB 1 at PRIORITY 2 [ TICKS 9 ALLOT 1 TIME 3 (of 22) ]
          [ time 159 ] IO_START by JOB 1
          IO DONE
          [ time 159 ] Run JOB 0 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 37 (of 178) ]
          [ time 160 ] Run JOB 0 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 36 (of 178) ]
          [ time 161 ] Run JOB 0 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 35 (of 178) ]
          [ time 162 ] Run JOB 0 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 34 (of 178) ]
          [ time 163 ] Run JOB 0 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 33 (of 178) ]
          [ time 164 ] IO_DONE by JOB 1
          [ time 164 ] Run JOB 1 at PRIORITY 2 [ TICKS 9 ALLOT 1 TIME 2 (of 22) ]
          [ time 165 ] IO_START by JOB 1
          IO DONE
          [ time 165 ] Run JOB 0 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 32 (of 178) ]
          [ time 166 ] Run JOB 0 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 31 (of 178) ]
          [ time 167 ] Run JOB 0 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 30 (of 178) ]
          [ time 168 ] Run JOB 0 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 29 (of 178) ]
          [ time 169 ] Run JOB 0 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 28 (of 178) ]
          [ time 170 ] IO_DONE by JOB 1
          [ time 170 ] Run JOB 1 at PRIORITY 2 [ TICKS 9 ALLOT 1 TIME 1 (of 22) ]
          [ time 171 ] IO_START by JOB 1
          IO DONE
          [ time 171 ] Run JOB 0 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 27 (of 178) ]
          [ time 172 ] Run JOB 0 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 26 (of 178) ]
          [ time 173 ] Run JOB 0 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 25 (of 178) ]
          [ time 174 ] Run JOB 0 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 24 (of 178) ]
          [ time 175 ] Run JOB 0 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 23 (of 178) ]
          [ time 176 ] IO_DONE by JOB 1
          [ time 176 ] Run JOB 1 at PRIORITY 2 [ TICKS 9 ALLOT 1 TIME 0 (of 22) ]
          [ time 177 ] FINISHED JOB 1
          [ time 177 ] Run JOB 0 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 22 (of 178) ]
          [ time 178 ] Run JOB 0 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 21 (of 178) ]
          [ time 179 ] Run JOB 0 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 20 (of 178) ]
          [ time 180 ] Run JOB 0 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 19 (of 178) ]
          [ time 181 ] Run JOB 0 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 18 (of 178) ]
          [ time 182 ] Run JOB 0 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 17 (of 178) ]
          [ time 183 ] Run JOB 0 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 16 (of 178) ]
          [ time 184 ] Run JOB 0 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 15 (of 178) ]
          [ time 185 ] Run JOB 0 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 14 (of 178) ]
          [ time 186 ] Run JOB 0 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 13 (of 178) ]
          [ time 187 ] Run JOB 0 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 12 (of 178) ]
          [ time 188 ] Run JOB 0 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 11 (of 178) ]
          [ time 189 ] Run JOB 0 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 10 (of 178) ]
          [ time 190 ] Run JOB 0 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 9 (of 178) ]
          [ time 191 ] Run JOB 0 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 8 (of 178) ]
          [ time 192 ] Run JOB 0 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 7 (of 178) ]
          [ time 193 ] Run JOB 0 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 6 (of 178) ]
          [ time 194 ] Run JOB 0 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 5 (of 178) ]
          [ time 195 ] Run JOB 0 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 4 (of 178) ]
          [ time 196 ] Run JOB 0 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 3 (of 178) ]
          [ time 197 ] Run JOB 0 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 2 (of 178) ]
          [ time 198 ] Run JOB 0 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 1 (of 178) ]
          [ time 199 ] Run JOB 0 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 0 (of 178) ]
          [ time 200 ] FINISHED JOB 0

          Final statistics:
            Job  0: startTime   0 - response   0 - turnaround 200
            Job  1: startTime  50 - response   0 - turnaround 127

            Avg  1: startTime n/a - response 0.00 - turnaround 163.50

    </details>
    </details>
    <br>

3.  How would you configure the scheduler parameters to behave just like a round-robin scheduler?

    <details>
    <summary>Answer</summary>
    <details>
    <summary>python mlfq.py --jlist 0,30,0:0,30,0 -Q 5,10,10 -A 2,1,1 -n 3 -c</summary>

          Here is the list of inputs:
          OPTIONS jobs 2
          OPTIONS queues 3
          OPTIONS allotments for queue  2 is   2
          OPTIONS quantum length for queue  2 is   5
          OPTIONS allotments for queue  1 is   1
          OPTIONS quantum length for queue  1 is  10
          OPTIONS allotments for queue  0 is   1
          OPTIONS quantum length for queue  0 is  10
          OPTIONS boost 0
          OPTIONS ioTime 5
          OPTIONS stayAfterIO False
          OPTIONS iobump False


          For each job, three defining characteristics are given:
            startTime : at what time does the job enter the system
            runTime   : the total CPU time needed by the job to finish
            ioFreq    : every ioFreq time units, the job issues an I/O
                        (the I/O takes ioTime units to complete)

          Job List:
            Job  0: startTime   0 - runTime  30 - ioFreq   0
            Job  1: startTime   0 - runTime  30 - ioFreq   0


          Execution Trace:

          [ time 0 ] JOB BEGINS by JOB 0
          [ time 0 ] JOB BEGINS by JOB 1
          [ time 0 ] Run JOB 0 at PRIORITY 2 [ TICKS 4 ALLOT 2 TIME 29 (of 30) ]
          [ time 1 ] Run JOB 0 at PRIORITY 2 [ TICKS 3 ALLOT 2 TIME 28 (of 30) ]
          [ time 2 ] Run JOB 0 at PRIORITY 2 [ TICKS 2 ALLOT 2 TIME 27 (of 30) ]
          [ time 3 ] Run JOB 0 at PRIORITY 2 [ TICKS 1 ALLOT 2 TIME 26 (of 30) ]
          [ time 4 ] Run JOB 0 at PRIORITY 2 [ TICKS 0 ALLOT 2 TIME 25 (of 30) ]
          [ time 5 ] Run JOB 1 at PRIORITY 2 [ TICKS 4 ALLOT 2 TIME 29 (of 30) ]
          [ time 6 ] Run JOB 1 at PRIORITY 2 [ TICKS 3 ALLOT 2 TIME 28 (of 30) ]
          [ time 7 ] Run JOB 1 at PRIORITY 2 [ TICKS 2 ALLOT 2 TIME 27 (of 30) ]
          [ time 8 ] Run JOB 1 at PRIORITY 2 [ TICKS 1 ALLOT 2 TIME 26 (of 30) ]
          [ time 9 ] Run JOB 1 at PRIORITY 2 [ TICKS 0 ALLOT 2 TIME 25 (of 30) ]
          [ time 10 ] Run JOB 0 at PRIORITY 2 [ TICKS 4 ALLOT 1 TIME 24 (of 30) ]
          [ time 11 ] Run JOB 0 at PRIORITY 2 [ TICKS 3 ALLOT 1 TIME 23 (of 30) ]
          [ time 12 ] Run JOB 0 at PRIORITY 2 [ TICKS 2 ALLOT 1 TIME 22 (of 30) ]
          [ time 13 ] Run JOB 0 at PRIORITY 2 [ TICKS 1 ALLOT 1 TIME 21 (of 30) ]
          [ time 14 ] Run JOB 0 at PRIORITY 2 [ TICKS 0 ALLOT 1 TIME 20 (of 30) ]
          [ time 15 ] Run JOB 1 at PRIORITY 2 [ TICKS 4 ALLOT 1 TIME 24 (of 30) ]
          [ time 16 ] Run JOB 1 at PRIORITY 2 [ TICKS 3 ALLOT 1 TIME 23 (of 30) ]
          [ time 17 ] Run JOB 1 at PRIORITY 2 [ TICKS 2 ALLOT 1 TIME 22 (of 30) ]
          [ time 18 ] Run JOB 1 at PRIORITY 2 [ TICKS 1 ALLOT 1 TIME 21 (of 30) ]
          [ time 19 ] Run JOB 1 at PRIORITY 2 [ TICKS 0 ALLOT 1 TIME 20 (of 30) ]
          [ time 20 ] Run JOB 0 at PRIORITY 1 [ TICKS 9 ALLOT 1 TIME 19 (of 30) ]
          [ time 21 ] Run JOB 0 at PRIORITY 1 [ TICKS 8 ALLOT 1 TIME 18 (of 30) ]
          [ time 22 ] Run JOB 0 at PRIORITY 1 [ TICKS 7 ALLOT 1 TIME 17 (of 30) ]
          [ time 23 ] Run JOB 0 at PRIORITY 1 [ TICKS 6 ALLOT 1 TIME 16 (of 30) ]
          [ time 24 ] Run JOB 0 at PRIORITY 1 [ TICKS 5 ALLOT 1 TIME 15 (of 30) ]
          [ time 25 ] Run JOB 0 at PRIORITY 1 [ TICKS 4 ALLOT 1 TIME 14 (of 30) ]
          [ time 26 ] Run JOB 0 at PRIORITY 1 [ TICKS 3 ALLOT 1 TIME 13 (of 30) ]
          [ time 27 ] Run JOB 0 at PRIORITY 1 [ TICKS 2 ALLOT 1 TIME 12 (of 30) ]
          [ time 28 ] Run JOB 0 at PRIORITY 1 [ TICKS 1 ALLOT 1 TIME 11 (of 30) ]
          [ time 29 ] Run JOB 0 at PRIORITY 1 [ TICKS 0 ALLOT 1 TIME 10 (of 30) ]
          [ time 30 ] Run JOB 1 at PRIORITY 1 [ TICKS 9 ALLOT 1 TIME 19 (of 30) ]
          [ time 31 ] Run JOB 1 at PRIORITY 1 [ TICKS 8 ALLOT 1 TIME 18 (of 30) ]
          [ time 32 ] Run JOB 1 at PRIORITY 1 [ TICKS 7 ALLOT 1 TIME 17 (of 30) ]
          [ time 33 ] Run JOB 1 at PRIORITY 1 [ TICKS 6 ALLOT 1 TIME 16 (of 30) ]
          [ time 34 ] Run JOB 1 at PRIORITY 1 [ TICKS 5 ALLOT 1 TIME 15 (of 30) ]
          [ time 35 ] Run JOB 1 at PRIORITY 1 [ TICKS 4 ALLOT 1 TIME 14 (of 30) ]
          [ time 36 ] Run JOB 1 at PRIORITY 1 [ TICKS 3 ALLOT 1 TIME 13 (of 30) ]
          [ time 37 ] Run JOB 1 at PRIORITY 1 [ TICKS 2 ALLOT 1 TIME 12 (of 30) ]
          [ time 38 ] Run JOB 1 at PRIORITY 1 [ TICKS 1 ALLOT 1 TIME 11 (of 30) ]
          [ time 39 ] Run JOB 1 at PRIORITY 1 [ TICKS 0 ALLOT 1 TIME 10 (of 30) ]
          [ time 40 ] Run JOB 0 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 9 (of 30) ]
          [ time 41 ] Run JOB 0 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 8 (of 30) ]
          [ time 42 ] Run JOB 0 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 7 (of 30) ]
          [ time 43 ] Run JOB 0 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 6 (of 30) ]
          [ time 44 ] Run JOB 0 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 5 (of 30) ]
          [ time 45 ] Run JOB 0 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 4 (of 30) ]
          [ time 46 ] Run JOB 0 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 3 (of 30) ]
          [ time 47 ] Run JOB 0 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 2 (of 30) ]
          [ time 48 ] Run JOB 0 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 1 (of 30) ]
          [ time 49 ] Run JOB 0 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 0 (of 30) ]
          [ time 50 ] FINISHED JOB 0
          [ time 50 ] Run JOB 1 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 9 (of 30) ]
          [ time 51 ] Run JOB 1 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 8 (of 30) ]
          [ time 52 ] Run JOB 1 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 7 (of 30) ]
          [ time 53 ] Run JOB 1 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 6 (of 30) ]
          [ time 54 ] Run JOB 1 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 5 (of 30) ]
          [ time 55 ] Run JOB 1 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 4 (of 30) ]
          [ time 56 ] Run JOB 1 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 3 (of 30) ]
          [ time 57 ] Run JOB 1 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 2 (of 30) ]
          [ time 58 ] Run JOB 1 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 1 (of 30) ]
          [ time 59 ] Run JOB 1 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 0 (of 30) ]
          [ time 60 ] FINISHED JOB 1

          Final statistics:
            Job  0: startTime   0 - response   0 - turnaround  50
            Job  1: startTime   0 - response   5 - turnaround  60

            Avg  1: startTime n/a - response 2.50 - turnaround 55.00

    </details>
    </details>
    <br>

4.  Craft a workload with two jobs and scheduler parameters so that one job takes advantage of the older Rules 4a and 4b (turned on
    with the -S flag) to game the scheduler and obtain 99% of the CPU over a particular time interval.

       <details>
       <summary>python mlfq.py -Q 10,10,10 -A 1,1,1 -B 0 -S -l 0,100,9:0,100,0 -c</summary>
       <summary>Job 0 "juega con el scheduler" al emitir operaciones de I/O justo antes de agotar su quantum, evitando así ser degradado de nivel; gracias al uso del flag -S, cada vez que completa una I/O regresa con su prioridad alta y allotment intactos, lo que le permite mantenerse en la cola de mayor prioridad. Al mismo tiempo, Job 1, que no emite I/O, es degradado rápidamente a niveles inferiores y pierde prioridad. Esta combinación permite que Job 0 controle la mayor parte del CPU, obteniendo fácilmente entre el 90 y 99% del tiempo total, especialmente cuando Job 1 queda relegado en la cola más baja del sistema.</summary>
       </details>
       <details>
       <summary>Answer</summary>
            Here is the list of inputs:
            OPTIONS jobs 2
            OPTIONS queues 3
            OPTIONS allotments for queue  2 is   1
            OPTIONS quantum length for queue  2 is  10
            OPTIONS allotments for queue  1 is   1
            OPTIONS quantum length for queue  1 is  10
            OPTIONS allotments for queue  0 is   1
            OPTIONS quantum length for queue  0 is  10
            OPTIONS boost 0
            OPTIONS ioTime 5
            OPTIONS stayAfterIO True
            OPTIONS iobump False

            For each job, three defining characteristics are given:
              startTime : at what time does the job enter the system
              runTime   : the total CPU time needed by the job to finish
              ioFreq    : every ioFreq time units, the job issues an I/O
                          (the I/O takes ioTime units to complete)

            Job List:
              Job  0: startTime   0 - runTime 100 - ioFreq   9
              Job  1: startTime   0 - runTime 100 - ioFreq   0


            Execution Trace:

            [ time 0 ] JOB BEGINS by JOB 0
            [ time 0 ] JOB BEGINS by JOB 1
            [ time 0 ] Run JOB 0 at PRIORITY 2 [ TICKS 9 ALLOT 1 TIME 99 (of 100) ]
            [ time 1 ] Run JOB 0 at PRIORITY 2 [ TICKS 8 ALLOT 1 TIME 98 (of 100) ]
            [ time 2 ] Run JOB 0 at PRIORITY 2 [ TICKS 7 ALLOT 1 TIME 97 (of 100) ]
            [ time 3 ] Run JOB 0 at PRIORITY 2 [ TICKS 6 ALLOT 1 TIME 96 (of 100) ]
            [ time 4 ] Run JOB 0 at PRIORITY 2 [ TICKS 5 ALLOT 1 TIME 95 (of 100) ]
            [ time 5 ] Run JOB 0 at PRIORITY 2 [ TICKS 4 ALLOT 1 TIME 94 (of 100) ]
            [ time 6 ] Run JOB 0 at PRIORITY 2 [ TICKS 3 ALLOT 1 TIME 93 (of 100) ]
            [ time 7 ] Run JOB 0 at PRIORITY 2 [ TICKS 2 ALLOT 1 TIME 92 (of 100) ]
            [ time 8 ] Run JOB 0 at PRIORITY 2 [ TICKS 1 ALLOT 1 TIME 91 (of 100) ]
            [ time 9 ] IO_START by JOB 0
            IO DONE
            [ time 9 ] Run JOB 1 at PRIORITY 2 [ TICKS 9 ALLOT 1 TIME 99 (of 100) ]
            [ time 10 ] Run JOB 1 at PRIORITY 2 [ TICKS 8 ALLOT 1 TIME 98 (of 100) ]
            [ time 11 ] Run JOB 1 at PRIORITY 2 [ TICKS 7 ALLOT 1 TIME 97 (of 100) ]
            [ time 12 ] Run JOB 1 at PRIORITY 2 [ TICKS 6 ALLOT 1 TIME 96 (of 100) ]
            [ time 13 ] Run JOB 1 at PRIORITY 2 [ TICKS 5 ALLOT 1 TIME 95 (of 100) ]
            [ time 14 ] IO_DONE by JOB 0
            [ time 14 ] Run JOB 1 at PRIORITY 2 [ TICKS 4 ALLOT 1 TIME 94 (of 100) ]
            [ time 15 ] Run JOB 1 at PRIORITY 2 [ TICKS 3 ALLOT 1 TIME 93 (of 100) ]
            [ time 16 ] Run JOB 1 at PRIORITY 2 [ TICKS 2 ALLOT 1 TIME 92 (of 100) ]
            [ time 17 ] Run JOB 1 at PRIORITY 2 [ TICKS 1 ALLOT 1 TIME 91 (of 100) ]
            [ time 18 ] Run JOB 1 at PRIORITY 2 [ TICKS 0 ALLOT 1 TIME 90 (of 100) ]
            [ time 19 ] Run JOB 0 at PRIORITY 2 [ TICKS 9 ALLOT 1 TIME 90 (of 100) ]
            [ time 20 ] Run JOB 0 at PRIORITY 2 [ TICKS 8 ALLOT 1 TIME 89 (of 100) ]
            [ time 21 ] Run JOB 0 at PRIORITY 2 [ TICKS 7 ALLOT 1 TIME 88 (of 100) ]
            [ time 22 ] Run JOB 0 at PRIORITY 2 [ TICKS 6 ALLOT 1 TIME 87 (of 100) ]
            [ time 23 ] Run JOB 0 at PRIORITY 2 [ TICKS 5 ALLOT 1 TIME 86 (of 100) ]
            [ time 24 ] Run JOB 0 at PRIORITY 2 [ TICKS 4 ALLOT 1 TIME 85 (of 100) ]
            [ time 25 ] Run JOB 0 at PRIORITY 2 [ TICKS 3 ALLOT 1 TIME 84 (of 100) ]
            [ time 26 ] Run JOB 0 at PRIORITY 2 [ TICKS 2 ALLOT 1 TIME 83 (of 100) ]
            [ time 27 ] Run JOB 0 at PRIORITY 2 [ TICKS 1 ALLOT 1 TIME 82 (of 100) ]
            [ time 28 ] IO_START by JOB 0
            IO DONE
            [ time 28 ] Run JOB 1 at PRIORITY 1 [ TICKS 9 ALLOT 1 TIME 89 (of 100) ]
            [ time 29 ] Run JOB 1 at PRIORITY 1 [ TICKS 8 ALLOT 1 TIME 88 (of 100) ]
            [ time 30 ] Run JOB 1 at PRIORITY 1 [ TICKS 7 ALLOT 1 TIME 87 (of 100) ]
            [ time 31 ] Run JOB 1 at PRIORITY 1 [ TICKS 6 ALLOT 1 TIME 86 (of 100) ]
            [ time 32 ] Run JOB 1 at PRIORITY 1 [ TICKS 5 ALLOT 1 TIME 85 (of 100) ]
            [ time 33 ] IO_DONE by JOB 0
            [ time 33 ] Run JOB 0 at PRIORITY 2 [ TICKS 9 ALLOT 1 TIME 81 (of 100) ]
            [ time 34 ] Run JOB 0 at PRIORITY 2 [ TICKS 8 ALLOT 1 TIME 80 (of 100) ]
            [ time 35 ] Run JOB 0 at PRIORITY 2 [ TICKS 7 ALLOT 1 TIME 79 (of 100) ]
            [ time 36 ] Run JOB 0 at PRIORITY 2 [ TICKS 6 ALLOT 1 TIME 78 (of 100) ]
            [ time 37 ] Run JOB 0 at PRIORITY 2 [ TICKS 5 ALLOT 1 TIME 77 (of 100) ]
            [ time 38 ] Run JOB 0 at PRIORITY 2 [ TICKS 4 ALLOT 1 TIME 76 (of 100) ]
            [ time 39 ] Run JOB 0 at PRIORITY 2 [ TICKS 3 ALLOT 1 TIME 75 (of 100) ]
            [ time 40 ] Run JOB 0 at PRIORITY 2 [ TICKS 2 ALLOT 1 TIME 74 (of 100) ]
            [ time 41 ] Run JOB 0 at PRIORITY 2 [ TICKS 1 ALLOT 1 TIME 73 (of 100) ]
            [ time 42 ] IO_START by JOB 0
            IO DONE
            [ time 42 ] Run JOB 1 at PRIORITY 1 [ TICKS 4 ALLOT 1 TIME 84 (of 100) ]
            [ time 43 ] Run JOB 1 at PRIORITY 1 [ TICKS 3 ALLOT 1 TIME 83 (of 100) ]
            [ time 44 ] Run JOB 1 at PRIORITY 1 [ TICKS 2 ALLOT 1 TIME 82 (of 100) ]
            [ time 45 ] Run JOB 1 at PRIORITY 1 [ TICKS 1 ALLOT 1 TIME 81 (of 100) ]
            [ time 46 ] Run JOB 1 at PRIORITY 1 [ TICKS 0 ALLOT 1 TIME 80 (of 100) ]
            [ time 47 ] IO_DONE by JOB 0
            [ time 47 ] Run JOB 0 at PRIORITY 2 [ TICKS 9 ALLOT 1 TIME 72 (of 100) ]
            [ time 48 ] Run JOB 0 at PRIORITY 2 [ TICKS 8 ALLOT 1 TIME 71 (of 100) ]
            [ time 49 ] Run JOB 0 at PRIORITY 2 [ TICKS 7 ALLOT 1 TIME 70 (of 100) ]
            [ time 50 ] Run JOB 0 at PRIORITY 2 [ TICKS 6 ALLOT 1 TIME 69 (of 100) ]
            [ time 51 ] Run JOB 0 at PRIORITY 2 [ TICKS 5 ALLOT 1 TIME 68 (of 100) ]
            [ time 52 ] Run JOB 0 at PRIORITY 2 [ TICKS 4 ALLOT 1 TIME 67 (of 100) ]
            [ time 53 ] Run JOB 0 at PRIORITY 2 [ TICKS 3 ALLOT 1 TIME 66 (of 100) ]
            [ time 54 ] Run JOB 0 at PRIORITY 2 [ TICKS 2 ALLOT 1 TIME 65 (of 100) ]
            [ time 55 ] Run JOB 0 at PRIORITY 2 [ TICKS 1 ALLOT 1 TIME 64 (of 100) ]
            [ time 56 ] IO_START by JOB 0
            IO DONE
            [ time 56 ] Run JOB 1 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 79 (of 100) ]
            [ time 57 ] Run JOB 1 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 78 (of 100) ]
            [ time 58 ] Run JOB 1 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 77 (of 100) ]
            [ time 59 ] Run JOB 1 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 76 (of 100) ]
            [ time 60 ] Run JOB 1 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 75 (of 100) ]
            [ time 61 ] IO_DONE by JOB 0
            [ time 61 ] Run JOB 0 at PRIORITY 2 [ TICKS 9 ALLOT 1 TIME 63 (of 100) ]
            [ time 62 ] Run JOB 0 at PRIORITY 2 [ TICKS 8 ALLOT 1 TIME 62 (of 100) ]
            [ time 63 ] Run JOB 0 at PRIORITY 2 [ TICKS 7 ALLOT 1 TIME 61 (of 100) ]
            [ time 64 ] Run JOB 0 at PRIORITY 2 [ TICKS 6 ALLOT 1 TIME 60 (of 100) ]
            [ time 65 ] Run JOB 0 at PRIORITY 2 [ TICKS 5 ALLOT 1 TIME 59 (of 100) ]
            [ time 66 ] Run JOB 0 at PRIORITY 2 [ TICKS 4 ALLOT 1 TIME 58 (of 100) ]
            [ time 67 ] Run JOB 0 at PRIORITY 2 [ TICKS 3 ALLOT 1 TIME 57 (of 100) ]
            [ time 68 ] Run JOB 0 at PRIORITY 2 [ TICKS 2 ALLOT 1 TIME 56 (of 100) ]
            [ time 69 ] Run JOB 0 at PRIORITY 2 [ TICKS 1 ALLOT 1 TIME 55 (of 100) ]
            [ time 70 ] IO_START by JOB 0
            IO DONE
            [ time 70 ] Run JOB 1 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 74 (of 100) ]
            [ time 71 ] Run JOB 1 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 73 (of 100) ]
            [ time 72 ] Run JOB 1 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 72 (of 100) ]
            [ time 73 ] Run JOB 1 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 71 (of 100) ]
            [ time 74 ] Run JOB 1 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 70 (of 100) ]
            [ time 75 ] IO_DONE by JOB 0
            [ time 75 ] Run JOB 0 at PRIORITY 2 [ TICKS 9 ALLOT 1 TIME 54 (of 100) ]
            [ time 76 ] Run JOB 0 at PRIORITY 2 [ TICKS 8 ALLOT 1 TIME 53 (of 100) ]
            [ time 77 ] Run JOB 0 at PRIORITY 2 [ TICKS 7 ALLOT 1 TIME 52 (of 100) ]
            [ time 78 ] Run JOB 0 at PRIORITY 2 [ TICKS 6 ALLOT 1 TIME 51 (of 100) ]
            [ time 79 ] Run JOB 0 at PRIORITY 2 [ TICKS 5 ALLOT 1 TIME 50 (of 100) ]
            [ time 80 ] Run JOB 0 at PRIORITY 2 [ TICKS 4 ALLOT 1 TIME 49 (of 100) ]
            [ time 81 ] Run JOB 0 at PRIORITY 2 [ TICKS 3 ALLOT 1 TIME 48 (of 100) ]
            [ time 82 ] Run JOB 0 at PRIORITY 2 [ TICKS 2 ALLOT 1 TIME 47 (of 100) ]
            [ time 83 ] Run JOB 0 at PRIORITY 2 [ TICKS 1 ALLOT 1 TIME 46 (of 100) ]
            [ time 84 ] IO_START by JOB 0
            IO DONE
            [ time 84 ] Run JOB 1 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 69 (of 100) ]
            [ time 85 ] Run JOB 1 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 68 (of 100) ]
            [ time 86 ] Run JOB 1 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 67 (of 100) ]
            [ time 87 ] Run JOB 1 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 66 (of 100) ]
            [ time 88 ] Run JOB 1 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 65 (of 100) ]
            [ time 89 ] IO_DONE by JOB 0
            [ time 89 ] Run JOB 0 at PRIORITY 2 [ TICKS 9 ALLOT 1 TIME 45 (of 100) ]
            [ time 90 ] Run JOB 0 at PRIORITY 2 [ TICKS 8 ALLOT 1 TIME 44 (of 100) ]
            [ time 91 ] Run JOB 0 at PRIORITY 2 [ TICKS 7 ALLOT 1 TIME 43 (of 100) ]
            [ time 92 ] Run JOB 0 at PRIORITY 2 [ TICKS 6 ALLOT 1 TIME 42 (of 100) ]
            [ time 93 ] Run JOB 0 at PRIORITY 2 [ TICKS 5 ALLOT 1 TIME 41 (of 100) ]
            [ time 94 ] Run JOB 0 at PRIORITY 2 [ TICKS 4 ALLOT 1 TIME 40 (of 100) ]
            [ time 95 ] Run JOB 0 at PRIORITY 2 [ TICKS 3 ALLOT 1 TIME 39 (of 100) ]
            [ time 96 ] Run JOB 0 at PRIORITY 2 [ TICKS 2 ALLOT 1 TIME 38 (of 100) ]
            [ time 97 ] Run JOB 0 at PRIORITY 2 [ TICKS 1 ALLOT 1 TIME 37 (of 100) ]
            [ time 98 ] IO_START by JOB 0
            IO DONE
            [ time 98 ] Run JOB 1 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 64 (of 100) ]
            [ time 99 ] Run JOB 1 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 63 (of 100) ]
            [ time 100 ] Run JOB 1 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 62 (of 100) ]
            [ time 101 ] Run JOB 1 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 61 (of 100) ]
            [ time 102 ] Run JOB 1 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 60 (of 100) ]
            [ time 103 ] IO_DONE by JOB 0
            [ time 103 ] Run JOB 0 at PRIORITY 2 [ TICKS 9 ALLOT 1 TIME 36 (of 100) ]
            [ time 104 ] Run JOB 0 at PRIORITY 2 [ TICKS 8 ALLOT 1 TIME 35 (of 100) ]
            [ time 105 ] Run JOB 0 at PRIORITY 2 [ TICKS 7 ALLOT 1 TIME 34 (of 100) ]
            [ time 106 ] Run JOB 0 at PRIORITY 2 [ TICKS 6 ALLOT 1 TIME 33 (of 100) ]
            [ time 107 ] Run JOB 0 at PRIORITY 2 [ TICKS 5 ALLOT 1 TIME 32 (of 100) ]
            [ time 108 ] Run JOB 0 at PRIORITY 2 [ TICKS 4 ALLOT 1 TIME 31 (of 100) ]
            [ time 109 ] Run JOB 0 at PRIORITY 2 [ TICKS 3 ALLOT 1 TIME 30 (of 100) ]
            [ time 110 ] Run JOB 0 at PRIORITY 2 [ TICKS 2 ALLOT 1 TIME 29 (of 100) ]
            [ time 111 ] Run JOB 0 at PRIORITY 2 [ TICKS 1 ALLOT 1 TIME 28 (of 100) ]
            [ time 112 ] IO_START by JOB 0
            IO DONE
            [ time 112 ] Run JOB 1 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 59 (of 100) ]
            [ time 113 ] Run JOB 1 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 58 (of 100) ]
            [ time 114 ] Run JOB 1 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 57 (of 100) ]
            [ time 115 ] Run JOB 1 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 56 (of 100) ]
            [ time 116 ] Run JOB 1 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 55 (of 100) ]
            [ time 117 ] IO_DONE by JOB 0
            [ time 117 ] Run JOB 0 at PRIORITY 2 [ TICKS 9 ALLOT 1 TIME 27 (of 100) ]
            [ time 118 ] Run JOB 0 at PRIORITY 2 [ TICKS 8 ALLOT 1 TIME 26 (of 100) ]
            [ time 119 ] Run JOB 0 at PRIORITY 2 [ TICKS 7 ALLOT 1 TIME 25 (of 100) ]
            [ time 120 ] Run JOB 0 at PRIORITY 2 [ TICKS 6 ALLOT 1 TIME 24 (of 100) ]
            [ time 121 ] Run JOB 0 at PRIORITY 2 [ TICKS 5 ALLOT 1 TIME 23 (of 100) ]
            [ time 122 ] Run JOB 0 at PRIORITY 2 [ TICKS 4 ALLOT 1 TIME 22 (of 100) ]
            [ time 123 ] Run JOB 0 at PRIORITY 2 [ TICKS 3 ALLOT 1 TIME 21 (of 100) ]
            [ time 124 ] Run JOB 0 at PRIORITY 2 [ TICKS 2 ALLOT 1 TIME 20 (of 100) ]
            [ time 125 ] Run JOB 0 at PRIORITY 2 [ TICKS 1 ALLOT 1 TIME 19 (of 100) ]
            [ time 126 ] IO_START by JOB 0
            IO DONE
            [ time 126 ] Run JOB 1 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 54 (of 100) ]
            [ time 127 ] Run JOB 1 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 53 (of 100) ]
            [ time 128 ] Run JOB 1 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 52 (of 100) ]
            [ time 129 ] Run JOB 1 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 51 (of 100) ]
            [ time 130 ] Run JOB 1 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 50 (of 100) ]
            [ time 131 ] IO_DONE by JOB 0
            [ time 131 ] Run JOB 0 at PRIORITY 2 [ TICKS 9 ALLOT 1 TIME 18 (of 100) ]
            [ time 132 ] Run JOB 0 at PRIORITY 2 [ TICKS 8 ALLOT 1 TIME 17 (of 100) ]
            [ time 133 ] Run JOB 0 at PRIORITY 2 [ TICKS 7 ALLOT 1 TIME 16 (of 100) ]
            [ time 134 ] Run JOB 0 at PRIORITY 2 [ TICKS 6 ALLOT 1 TIME 15 (of 100) ]
            [ time 135 ] Run JOB 0 at PRIORITY 2 [ TICKS 5 ALLOT 1 TIME 14 (of 100) ]
            [ time 136 ] Run JOB 0 at PRIORITY 2 [ TICKS 4 ALLOT 1 TIME 13 (of 100) ]
            [ time 137 ] Run JOB 0 at PRIORITY 2 [ TICKS 3 ALLOT 1 TIME 12 (of 100) ]
            [ time 138 ] Run JOB 0 at PRIORITY 2 [ TICKS 2 ALLOT 1 TIME 11 (of 100) ]
            [ time 139 ] Run JOB 0 at PRIORITY 2 [ TICKS 1 ALLOT 1 TIME 10 (of 100) ]
            [ time 140 ] IO_START by JOB 0
            IO DONE
            [ time 140 ] Run JOB 1 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 49 (of 100) ]
            [ time 141 ] Run JOB 1 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 48 (of 100) ]
            [ time 142 ] Run JOB 1 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 47 (of 100) ]
            [ time 143 ] Run JOB 1 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 46 (of 100) ]
            [ time 144 ] Run JOB 1 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 45 (of 100) ]
            [ time 145 ] IO_DONE by JOB 0
            [ time 145 ] Run JOB 0 at PRIORITY 2 [ TICKS 9 ALLOT 1 TIME 9 (of 100) ]
            [ time 146 ] Run JOB 0 at PRIORITY 2 [ TICKS 8 ALLOT 1 TIME 8 (of 100) ]
            [ time 147 ] Run JOB 0 at PRIORITY 2 [ TICKS 7 ALLOT 1 TIME 7 (of 100) ]
            [ time 148 ] Run JOB 0 at PRIORITY 2 [ TICKS 6 ALLOT 1 TIME 6 (of 100) ]
            [ time 149 ] Run JOB 0 at PRIORITY 2 [ TICKS 5 ALLOT 1 TIME 5 (of 100) ]
            [ time 150 ] Run JOB 0 at PRIORITY 2 [ TICKS 4 ALLOT 1 TIME 4 (of 100) ]
            [ time 151 ] Run JOB 0 at PRIORITY 2 [ TICKS 3 ALLOT 1 TIME 3 (of 100) ]
            [ time 152 ] Run JOB 0 at PRIORITY 2 [ TICKS 2 ALLOT 1 TIME 2 (of 100) ]
            [ time 153 ] Run JOB 0 at PRIORITY 2 [ TICKS 1 ALLOT 1 TIME 1 (of 100) ]
            [ time 154 ] IO_START by JOB 0
            IO DONE
            [ time 154 ] Run JOB 1 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 44 (of 100) ]
            [ time 155 ] Run JOB 1 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 43 (of 100) ]
            [ time 156 ] Run JOB 1 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 42 (of 100) ]
            [ time 157 ] Run JOB 1 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 41 (of 100) ]
            [ time 158 ] Run JOB 1 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 40 (of 100) ]
            [ time 159 ] IO_DONE by JOB 0
            [ time 159 ] Run JOB 0 at PRIORITY 2 [ TICKS 9 ALLOT 1 TIME 0 (of 100) ]
            [ time 160 ] FINISHED JOB 0
            [ time 160 ] Run JOB 1 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 39 (of 100) ]
            [ time 161 ] Run JOB 1 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 38 (of 100) ]
            [ time 162 ] Run JOB 1 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 37 (of 100) ]
            [ time 163 ] Run JOB 1 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 36 (of 100) ]
            [ time 164 ] Run JOB 1 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 35 (of 100) ]
            [ time 165 ] Run JOB 1 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 34 (of 100) ]
            [ time 166 ] Run JOB 1 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 33 (of 100) ]
            [ time 167 ] Run JOB 1 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 32 (of 100) ]
            [ time 168 ] Run JOB 1 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 31 (of 100) ]
            [ time 169 ] Run JOB 1 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 30 (of 100) ]
            [ time 170 ] Run JOB 1 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 29 (of 100) ]
            [ time 171 ] Run JOB 1 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 28 (of 100) ]
            [ time 172 ] Run JOB 1 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 27 (of 100) ]
            [ time 173 ] Run JOB 1 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 26 (of 100) ]
            [ time 174 ] Run JOB 1 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 25 (of 100) ]
            [ time 175 ] Run JOB 1 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 24 (of 100) ]
            [ time 176 ] Run JOB 1 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 23 (of 100) ]
            [ time 177 ] Run JOB 1 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 22 (of 100) ]
            [ time 178 ] Run JOB 1 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 21 (of 100) ]
            [ time 179 ] Run JOB 1 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 20 (of 100) ]
            [ time 180 ] Run JOB 1 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 19 (of 100) ]
            [ time 181 ] Run JOB 1 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 18 (of 100) ]
            [ time 182 ] Run JOB 1 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 17 (of 100) ]
            [ time 183 ] Run JOB 1 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 16 (of 100) ]
            [ time 184 ] Run JOB 1 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 15 (of 100) ]
            [ time 185 ] Run JOB 1 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 14 (of 100) ]
            [ time 186 ] Run JOB 1 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 13 (of 100) ]
            [ time 187 ] Run JOB 1 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 12 (of 100) ]
            [ time 188 ] Run JOB 1 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 11 (of 100) ]
            [ time 189 ] Run JOB 1 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 10 (of 100) ]
            [ time 190 ] Run JOB 1 at PRIORITY 0 [ TICKS 9 ALLOT 1 TIME 9 (of 100) ]
            [ time 191 ] Run JOB 1 at PRIORITY 0 [ TICKS 8 ALLOT 1 TIME 8 (of 100) ]
            [ time 192 ] Run JOB 1 at PRIORITY 0 [ TICKS 7 ALLOT 1 TIME 7 (of 100) ]
            [ time 193 ] Run JOB 1 at PRIORITY 0 [ TICKS 6 ALLOT 1 TIME 6 (of 100) ]
            [ time 194 ] Run JOB 1 at PRIORITY 0 [ TICKS 5 ALLOT 1 TIME 5 (of 100) ]
            [ time 195 ] Run JOB 1 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 4 (of 100) ]
            [ time 196 ] Run JOB 1 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 3 (of 100) ]
            [ time 197 ] Run JOB 1 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 2 (of 100) ]
            [ time 198 ] Run JOB 1 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 1 (of 100) ]
            [ time 199 ] Run JOB 1 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 0 (of 100) ]
            [ time 200 ] FINISHED JOB 1

            Final statistics:
              Job  0: startTime   0 - response   0 - turnaround 160
              Job  1: startTime   0 - response   9 - turnaround 200

              Avg  1: startTime n/a - response 4.50 - turnaround 180.00

       </details>
       <br>

5.  Given a system with a quantum length of 10 ms in its highest queue, how often would you have to boost jobs back to the highest priority level (with the `-B` flag) in order to guarantee that a single longrunning (and potentially-starving) job gets at least 5% of the CPU?

    <summary>python mlfq.py -Q 1,1,1 -A 1,1,1 -B 20 -l 0,20,0:0,5,2 -S -c</summary>
    Job 0 corre inicialmente 1 ms en PRIORITY 2, pero es rápidamente degradado a PRIORITY 1 y luego a PRIORITY 0, donde permanece la mayor parte del tiempo; mientras tanto, Job 1, al hacer I/O cada 2 ms, logra mantenerse en prioridad alta y dominar el CPU. Sin embargo, en el tiempo 20 se aplica el BOOST, lo que permite que Job 0 regrese a PRIORITY 2 y continúe ejecutándose hasta finalizar en el tiempo 25.
    Job 0 recibió al menos 5% del CPU: se ejecutó 20 ms totales sobre un tiempo de simulación de 25 ms.
    El boost en time 20 garantizó que no quedara estancado.

    <details>
      <summary>Answer</summary>
              Here is the list of inputs:
              OPTIONS jobs 2
              OPTIONS queues 3
              OPTIONS allotments for queue  2 is   1
              OPTIONS quantum length for queue  2 is   1
              OPTIONS allotments for queue  1 is   1
              OPTIONS quantum length for queue  1 is   1
              OPTIONS allotments for queue  0 is   1
              OPTIONS quantum length for queue  0 is   1
              OPTIONS boost 20
              OPTIONS ioTime 5
              OPTIONS stayAfterIO True
              OPTIONS iobump False

          For each job, three defining characteristics are given:
            startTime : at what time does the job enter the system
            runTime   : the total CPU time needed by the job to finish
            ioFreq    : every ioFreq time units, the job issues an I/O
                        (the I/O takes ioTime units to complete)

          Job List:
            Job  0: startTime   0 - runTime  20 - ioFreq   0
            Job  1: startTime   0 - runTime   5 - ioFreq   2


          Execution Trace:

          [ time 0 ] JOB BEGINS by JOB 0
          [ time 0 ] JOB BEGINS by JOB 1
          [ time 0 ] Run JOB 0 at PRIORITY 2 [ TICKS 0 ALLOT 1 TIME 19 (of 20) ]
          [ time 1 ] Run JOB 1 at PRIORITY 2 [ TICKS 0 ALLOT 1 TIME 4 (of 5) ]
          [ time 2 ] Run JOB 0 at PRIORITY 1 [ TICKS 0 ALLOT 1 TIME 18 (of 20) ]
          [ time 3 ] Run JOB 1 at PRIORITY 1 [ TICKS 0 ALLOT 1 TIME 3 (of 5) ]
          [ time 4 ] IO_START by JOB 1
          IO DONE
          [ time 4 ] Run JOB 0 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 17 (of 20) ]
          [ time 5 ] Run JOB 0 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 16 (of 20) ]
          [ time 6 ] Run JOB 0 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 15 (of 20) ]
          [ time 7 ] Run JOB 0 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 14 (of 20) ]
          [ time 8 ] Run JOB 0 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 13 (of 20) ]
          [ time 9 ] IO_DONE by JOB 1
          [ time 9 ] Run JOB 0 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 12 (of 20) ]
          [ time 10 ] Run JOB 1 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 2 (of 5) ]
          [ time 11 ] Run JOB 0 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 11 (of 20) ]
          [ time 12 ] Run JOB 1 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 1 (of 5) ]
          [ time 13 ] IO_START by JOB 1
          IO DONE
          [ time 13 ] Run JOB 0 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 10 (of 20) ]
          [ time 14 ] Run JOB 0 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 9 (of 20) ]
          [ time 15 ] Run JOB 0 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 8 (of 20) ]
          [ time 16 ] Run JOB 0 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 7 (of 20) ]
          [ time 17 ] Run JOB 0 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 6 (of 20) ]
          [ time 18 ] IO_DONE by JOB 1
          [ time 18 ] Run JOB 0 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 5 (of 20) ]
          [ time 19 ] Run JOB 1 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 0 (of 5) ]
          [ time 20 ] FINISHED JOB 1
          [ time 20 ] BOOST ( every 20 )
          [ time 20 ] Run JOB 0 at PRIORITY 2 [ TICKS 0 ALLOT 1 TIME 4 (of 20) ]
          [ time 21 ] Run JOB 0 at PRIORITY 1 [ TICKS 0 ALLOT 1 TIME 3 (of 20) ]
          [ time 22 ] Run JOB 0 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 2 (of 20) ]
          [ time 23 ] Run JOB 0 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 1 (of 20) ]
          [ time 24 ] Run JOB 0 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 0 (of 20) ]
          [ time 25 ] FINISHED JOB 0

          Final statistics:
            Job  0: startTime   0 - response   0 - turnaround  25
            Job  1: startTime   0 - response   1 - turnaround  20

            Avg  1: startTime n/a - response 0.50 - turnaround 22.50

    </details>
    <br>

6.  One question that arises in scheduling is which end of a queue to add a job that just finished I/O; the -I flag changes this behavior
    for this scheduling simulator. Play around with some workloads and see if you can see the effect of this flag.

    La opción -I en el simulador de planificación cambia el comportamiento al reinsertar un job que acaba de finalizar una operación de I/O: sin -I, el job se agrega al final de su cola de prioridad, por lo que debe esperar su turno detrás de otros jobs; con -I, el job se coloca al inicio de la cola, permitiéndole adelantarse y posiblemente ejecutar inmediatamente
     <details>
     <summary>Sin utilizar la Flag I, python mlfq.py -Q 5,5,5 -A 1,1,1 -B 0 -l 0,30,4:0,30,0 -S -c</summary>
             Here is the list of inputs:
         OPTIONS jobs 2
         OPTIONS queues 3
         OPTIONS allotments for queue  2 is   1
         OPTIONS quantum length for queue  2 is   5
         OPTIONS allotments for queue  1 is   1
         OPTIONS quantum length for queue  1 is   5
         OPTIONS allotments for queue  0 is   1
         OPTIONS quantum length for queue  0 is   5
         OPTIONS boost 0
         OPTIONS ioTime 5
         OPTIONS stayAfterIO True
         OPTIONS iobump False

         For each job, three defining characteristics are given:
           startTime : at what time does the job enter the system
           runTime   : the total CPU time needed by the job to finish
           ioFreq    : every ioFreq time units, the job issues an I/O
                       (the I/O takes ioTime units to complete)

         Job List:
           Job  0: startTime   0 - runTime  30 - ioFreq   4
           Job  1: startTime   0 - runTime  30 - ioFreq   0


         Execution Trace:

         [ time 0 ] JOB BEGINS by JOB 0
         [ time 0 ] JOB BEGINS by JOB 1
         [ time 0 ] Run JOB 0 at PRIORITY 2 [ TICKS 4 ALLOT 1 TIME 29 (of 30) ]
         [ time 1 ] Run JOB 0 at PRIORITY 2 [ TICKS 3 ALLOT 1 TIME 28 (of 30) ]
         [ time 2 ] Run JOB 0 at PRIORITY 2 [ TICKS 2 ALLOT 1 TIME 27 (of 30) ]
         [ time 3 ] Run JOB 0 at PRIORITY 2 [ TICKS 1 ALLOT 1 TIME 26 (of 30) ]
         [ time 4 ] IO_START by JOB 0
         IO DONE
         [ time 4 ] Run JOB 1 at PRIORITY 2 [ TICKS 4 ALLOT 1 TIME 29 (of 30) ]
         [ time 5 ] Run JOB 1 at PRIORITY 2 [ TICKS 3 ALLOT 1 TIME 28 (of 30) ]
         [ time 6 ] Run JOB 1 at PRIORITY 2 [ TICKS 2 ALLOT 1 TIME 27 (of 30) ]
         [ time 7 ] Run JOB 1 at PRIORITY 2 [ TICKS 1 ALLOT 1 TIME 26 (of 30) ]
         [ time 8 ] Run JOB 1 at PRIORITY 2 [ TICKS 0 ALLOT 1 TIME 25 (of 30) ]
         [ time 9 ] IO_DONE by JOB 0
         [ time 9 ] Run JOB 0 at PRIORITY 2 [ TICKS 4 ALLOT 1 TIME 25 (of 30) ]
         [ time 10 ] Run JOB 0 at PRIORITY 2 [ TICKS 3 ALLOT 1 TIME 24 (of 30) ]
         [ time 11 ] Run JOB 0 at PRIORITY 2 [ TICKS 2 ALLOT 1 TIME 23 (of 30) ]
         [ time 12 ] Run JOB 0 at PRIORITY 2 [ TICKS 1 ALLOT 1 TIME 22 (of 30) ]
         [ time 13 ] IO_START by JOB 0
         IO DONE
         [ time 13 ] Run JOB 1 at PRIORITY 1 [ TICKS 4 ALLOT 1 TIME 24 (of 30) ]
         [ time 14 ] Run JOB 1 at PRIORITY 1 [ TICKS 3 ALLOT 1 TIME 23 (of 30) ]
         [ time 15 ] Run JOB 1 at PRIORITY 1 [ TICKS 2 ALLOT 1 TIME 22 (of 30) ]
         [ time 16 ] Run JOB 1 at PRIORITY 1 [ TICKS 1 ALLOT 1 TIME 21 (of 30) ]
         [ time 17 ] Run JOB 1 at PRIORITY 1 [ TICKS 0 ALLOT 1 TIME 20 (of 30) ]
         [ time 18 ] IO_DONE by JOB 0
         [ time 18 ] Run JOB 0 at PRIORITY 2 [ TICKS 4 ALLOT 1 TIME 21 (of 30) ]
         [ time 19 ] Run JOB 0 at PRIORITY 2 [ TICKS 3 ALLOT 1 TIME 20 (of 30) ]
         [ time 20 ] Run JOB 0 at PRIORITY 2 [ TICKS 2 ALLOT 1 TIME 19 (of 30) ]
         [ time 21 ] Run JOB 0 at PRIORITY 2 [ TICKS 1 ALLOT 1 TIME 18 (of 30) ]
         [ time 22 ] IO_START by JOB 0
         IO DONE
         [ time 22 ] Run JOB 1 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 19 (of 30) ]
         [ time 23 ] Run JOB 1 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 18 (of 30) ]
         [ time 24 ] Run JOB 1 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 17 (of 30) ]
         [ time 25 ] Run JOB 1 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 16 (of 30) ]
         [ time 26 ] Run JOB 1 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 15 (of 30) ]
         [ time 27 ] IO_DONE by JOB 0
         [ time 27 ] Run JOB 0 at PRIORITY 2 [ TICKS 4 ALLOT 1 TIME 17 (of 30) ]
         [ time 28 ] Run JOB 0 at PRIORITY 2 [ TICKS 3 ALLOT 1 TIME 16 (of 30) ]
         [ time 29 ] Run JOB 0 at PRIORITY 2 [ TICKS 2 ALLOT 1 TIME 15 (of 30) ]
         [ time 30 ] Run JOB 0 at PRIORITY 2 [ TICKS 1 ALLOT 1 TIME 14 (of 30) ]
         [ time 31 ] IO_START by JOB 0
         IO DONE
         [ time 31 ] Run JOB 1 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 14 (of 30) ]
         [ time 32 ] Run JOB 1 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 13 (of 30) ]
         [ time 33 ] Run JOB 1 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 12 (of 30) ]
         [ time 34 ] Run JOB 1 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 11 (of 30) ]
         [ time 35 ] Run JOB 1 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 10 (of 30) ]
         [ time 36 ] IO_DONE by JOB 0
         [ time 36 ] Run JOB 0 at PRIORITY 2 [ TICKS 4 ALLOT 1 TIME 13 (of 30) ]
         [ time 37 ] Run JOB 0 at PRIORITY 2 [ TICKS 3 ALLOT 1 TIME 12 (of 30) ]
         [ time 38 ] Run JOB 0 at PRIORITY 2 [ TICKS 2 ALLOT 1 TIME 11 (of 30) ]
         [ time 39 ] Run JOB 0 at PRIORITY 2 [ TICKS 1 ALLOT 1 TIME 10 (of 30) ]
         [ time 40 ] IO_START by JOB 0
         IO DONE
         [ time 40 ] Run JOB 1 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 9 (of 30) ]
         [ time 41 ] Run JOB 1 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 8 (of 30) ]
         [ time 42 ] Run JOB 1 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 7 (of 30) ]
         [ time 43 ] Run JOB 1 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 6 (of 30) ]
         [ time 44 ] Run JOB 1 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 5 (of 30) ]
         [ time 45 ] IO_DONE by JOB 0
         [ time 45 ] Run JOB 0 at PRIORITY 2 [ TICKS 4 ALLOT 1 TIME 9 (of 30) ]
         [ time 46 ] Run JOB 0 at PRIORITY 2 [ TICKS 3 ALLOT 1 TIME 8 (of 30) ]
         [ time 47 ] Run JOB 0 at PRIORITY 2 [ TICKS 2 ALLOT 1 TIME 7 (of 30) ]
         [ time 48 ] Run JOB 0 at PRIORITY 2 [ TICKS 1 ALLOT 1 TIME 6 (of 30) ]
         [ time 49 ] IO_START by JOB 0
         IO DONE
         [ time 49 ] Run JOB 1 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 4 (of 30) ]
         [ time 50 ] Run JOB 1 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 3 (of 30) ]
         [ time 51 ] Run JOB 1 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 2 (of 30) ]
         [ time 52 ] Run JOB 1 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 1 (of 30) ]
         [ time 53 ] Run JOB 1 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 0 (of 30) ]
         [ time 54 ] FINISHED JOB 1
         [ time 54 ] IO_DONE by JOB 0
         [ time 54 ] Run JOB 0 at PRIORITY 2 [ TICKS 4 ALLOT 1 TIME 5 (of 30) ]
         [ time 55 ] Run JOB 0 at PRIORITY 2 [ TICKS 3 ALLOT 1 TIME 4 (of 30) ]
         [ time 56 ] Run JOB 0 at PRIORITY 2 [ TICKS 2 ALLOT 1 TIME 3 (of 30) ]
         [ time 57 ] Run JOB 0 at PRIORITY 2 [ TICKS 1 ALLOT 1 TIME 2 (of 30) ]
         [ time 58 ] IO_START by JOB 0
         IO DONE
         [ time 58 ] IDLE
         [ time 59 ] IDLE
         [ time 60 ] IDLE
         [ time 61 ] IDLE
         [ time 62 ] IDLE
         [ time 63 ] IO_DONE by JOB 0
         [ time 63 ] Run JOB 0 at PRIORITY 2 [ TICKS 4 ALLOT 1 TIME 1 (of 30) ]
         [ time 64 ] Run JOB 0 at PRIORITY 2 [ TICKS 3 ALLOT 1 TIME 0 (of 30) ]
         [ time 65 ] FINISHED JOB 0

         Final statistics:
           Job  0: startTime   0 - response   0 - turnaround  65
           Job  1: startTime   0 - response   4 - turnaround  54

           Avg  1: startTime n/a - response 2.00 - turnaround 59.50

     </details>
     <details>
     <summary>Utilizando la Flag I, python mlfq.py -Q 5,5,5 -A 1,1,1 -B 0 -l 0,30,4:0,30,0 -S -I -c</summary>
        Here is the list of inputs:
        OPTIONS jobs 2
        OPTIONS queues 3
        OPTIONS allotments for queue  2 is   1
        OPTIONS quantum length for queue  2 is   5
        OPTIONS allotments for queue  1 is   1
        OPTIONS quantum length for queue  1 is   5
        OPTIONS allotments for queue  0 is   1
        OPTIONS quantum length for queue  0 is   5
        OPTIONS boost 0
        OPTIONS ioTime 5
        OPTIONS stayAfterIO True
        OPTIONS iobump True

        For each job, three defining characteristics are given:
          startTime : at what time does the job enter the system
          runTime   : the total CPU time needed by the job to finish
          ioFreq    : every ioFreq time units, the job issues an I/O
                      (the I/O takes ioTime units to complete)

        Job List:
          Job  0: startTime   0 - runTime  30 - ioFreq   4
          Job  1: startTime   0 - runTime  30 - ioFreq   0


        Execution Trace:

        [ time 0 ] JOB BEGINS by JOB 0
        [ time 0 ] JOB BEGINS by JOB 1
        [ time 0 ] Run JOB 0 at PRIORITY 2 [ TICKS 4 ALLOT 1 TIME 29 (of 30) ]
        [ time 1 ] Run JOB 0 at PRIORITY 2 [ TICKS 3 ALLOT 1 TIME 28 (of 30) ]
        [ time 2 ] Run JOB 0 at PRIORITY 2 [ TICKS 2 ALLOT 1 TIME 27 (of 30) ]
        [ time 3 ] Run JOB 0 at PRIORITY 2 [ TICKS 1 ALLOT 1 TIME 26 (of 30) ]
        [ time 4 ] IO_START by JOB 0
        IO DONE
        [ time 4 ] Run JOB 1 at PRIORITY 2 [ TICKS 4 ALLOT 1 TIME 29 (of 30) ]
        [ time 5 ] Run JOB 1 at PRIORITY 2 [ TICKS 3 ALLOT 1 TIME 28 (of 30) ]
        [ time 6 ] Run JOB 1 at PRIORITY 2 [ TICKS 2 ALLOT 1 TIME 27 (of 30) ]
        [ time 7 ] Run JOB 1 at PRIORITY 2 [ TICKS 1 ALLOT 1 TIME 26 (of 30) ]
        [ time 8 ] Run JOB 1 at PRIORITY 2 [ TICKS 0 ALLOT 1 TIME 25 (of 30) ]
        [ time 9 ] IO_DONE by JOB 0
        [ time 9 ] Run JOB 0 at PRIORITY 2 [ TICKS 4 ALLOT 1 TIME 25 (of 30) ]
        [ time 10 ] Run JOB 0 at PRIORITY 2 [ TICKS 3 ALLOT 1 TIME 24 (of 30) ]
        [ time 11 ] Run JOB 0 at PRIORITY 2 [ TICKS 2 ALLOT 1 TIME 23 (of 30) ]
        [ time 12 ] Run JOB 0 at PRIORITY 2 [ TICKS 1 ALLOT 1 TIME 22 (of 30) ]
        [ time 13 ] IO_START by JOB 0
        IO DONE
        [ time 13 ] Run JOB 1 at PRIORITY 1 [ TICKS 4 ALLOT 1 TIME 24 (of 30) ]
        [ time 14 ] Run JOB 1 at PRIORITY 1 [ TICKS 3 ALLOT 1 TIME 23 (of 30) ]
        [ time 15 ] Run JOB 1 at PRIORITY 1 [ TICKS 2 ALLOT 1 TIME 22 (of 30) ]
        [ time 16 ] Run JOB 1 at PRIORITY 1 [ TICKS 1 ALLOT 1 TIME 21 (of 30) ]
        [ time 17 ] Run JOB 1 at PRIORITY 1 [ TICKS 0 ALLOT 1 TIME 20 (of 30) ]
        [ time 18 ] IO_DONE by JOB 0
        [ time 18 ] Run JOB 0 at PRIORITY 2 [ TICKS 4 ALLOT 1 TIME 21 (of 30) ]
        [ time 19 ] Run JOB 0 at PRIORITY 2 [ TICKS 3 ALLOT 1 TIME 20 (of 30) ]
        [ time 20 ] Run JOB 0 at PRIORITY 2 [ TICKS 2 ALLOT 1 TIME 19 (of 30) ]
        [ time 21 ] Run JOB 0 at PRIORITY 2 [ TICKS 1 ALLOT 1 TIME 18 (of 30) ]
        [ time 22 ] IO_START by JOB 0
        IO DONE
        [ time 22 ] Run JOB 1 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 19 (of 30) ]
        [ time 23 ] Run JOB 1 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 18 (of 30) ]
        [ time 24 ] Run JOB 1 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 17 (of 30) ]
        [ time 25 ] Run JOB 1 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 16 (of 30) ]
        [ time 26 ] Run JOB 1 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 15 (of 30) ]
        [ time 27 ] IO_DONE by JOB 0
        [ time 27 ] Run JOB 0 at PRIORITY 2 [ TICKS 4 ALLOT 1 TIME 17 (of 30) ]
        [ time 28 ] Run JOB 0 at PRIORITY 2 [ TICKS 3 ALLOT 1 TIME 16 (of 30) ]
        [ time 29 ] Run JOB 0 at PRIORITY 2 [ TICKS 2 ALLOT 1 TIME 15 (of 30) ]
        [ time 30 ] Run JOB 0 at PRIORITY 2 [ TICKS 1 ALLOT 1 TIME 14 (of 30) ]
        [ time 31 ] IO_START by JOB 0
        IO DONE
        [ time 31 ] Run JOB 1 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 14 (of 30) ]
        [ time 32 ] Run JOB 1 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 13 (of 30) ]
        [ time 33 ] Run JOB 1 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 12 (of 30) ]
        [ time 34 ] Run JOB 1 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 11 (of 30) ]
        [ time 35 ] Run JOB 1 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 10 (of 30) ]
        [ time 36 ] IO_DONE by JOB 0
        [ time 36 ] Run JOB 0 at PRIORITY 2 [ TICKS 4 ALLOT 1 TIME 13 (of 30) ]
        [ time 37 ] Run JOB 0 at PRIORITY 2 [ TICKS 3 ALLOT 1 TIME 12 (of 30) ]
        [ time 38 ] Run JOB 0 at PRIORITY 2 [ TICKS 2 ALLOT 1 TIME 11 (of 30) ]
        [ time 39 ] Run JOB 0 at PRIORITY 2 [ TICKS 1 ALLOT 1 TIME 10 (of 30) ]
        [ time 40 ] IO_START by JOB 0
        IO DONE
        [ time 40 ] Run JOB 1 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 9 (of 30) ]
        [ time 41 ] Run JOB 1 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 8 (of 30) ]
        [ time 42 ] Run JOB 1 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 7 (of 30) ]
        [ time 43 ] Run JOB 1 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 6 (of 30) ]
        [ time 44 ] Run JOB 1 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 5 (of 30) ]
        [ time 45 ] IO_DONE by JOB 0
        [ time 45 ] Run JOB 0 at PRIORITY 2 [ TICKS 4 ALLOT 1 TIME 9 (of 30) ]
        [ time 46 ] Run JOB 0 at PRIORITY 2 [ TICKS 3 ALLOT 1 TIME 8 (of 30) ]
        [ time 47 ] Run JOB 0 at PRIORITY 2 [ TICKS 2 ALLOT 1 TIME 7 (of 30) ]
        [ time 48 ] Run JOB 0 at PRIORITY 2 [ TICKS 1 ALLOT 1 TIME 6 (of 30) ]
        [ time 49 ] IO_START by JOB 0
        IO DONE
        [ time 49 ] Run JOB 1 at PRIORITY 0 [ TICKS 4 ALLOT 1 TIME 4 (of 30) ]
        [ time 50 ] Run JOB 1 at PRIORITY 0 [ TICKS 3 ALLOT 1 TIME 3 (of 30) ]
        [ time 51 ] Run JOB 1 at PRIORITY 0 [ TICKS 2 ALLOT 1 TIME 2 (of 30) ]
        [ time 52 ] Run JOB 1 at PRIORITY 0 [ TICKS 1 ALLOT 1 TIME 1 (of 30) ]
        [ time 53 ] Run JOB 1 at PRIORITY 0 [ TICKS 0 ALLOT 1 TIME 0 (of 30) ]
        [ time 54 ] FINISHED JOB 1
        [ time 54 ] IO_DONE by JOB 0
        [ time 54 ] Run JOB 0 at PRIORITY 2 [ TICKS 4 ALLOT 1 TIME 5 (of 30) ]
        [ time 55 ] Run JOB 0 at PRIORITY 2 [ TICKS 3 ALLOT 1 TIME 4 (of 30) ]
        [ time 56 ] Run JOB 0 at PRIORITY 2 [ TICKS 2 ALLOT 1 TIME 3 (of 30) ]
        [ time 57 ] Run JOB 0 at PRIORITY 2 [ TICKS 1 ALLOT 1 TIME 2 (of 30) ]
        [ time 58 ] IO_START by JOB 0
        IO DONE
        [ time 58 ] IDLE
        [ time 59 ] IDLE
        [ time 60 ] IDLE
        [ time 61 ] IDLE
        [ time 62 ] IDLE
        [ time 63 ] IO_DONE by JOB 0
        [ time 63 ] Run JOB 0 at PRIORITY 2 [ TICKS 4 ALLOT 1 TIME 1 (of 30) ]
        [ time 64 ] Run JOB 0 at PRIORITY 2 [ TICKS 3 ALLOT 1 TIME 0 (of 30) ]
        [ time 65 ] FINISHED JOB 0

        Final statistics:
          Job  0: startTime   0 - response   0 - turnaround  65
          Job  1: startTime   0 - response   4 - turnaround  54

          Avg  1: startTime n/a - response 2.00 - turnaround 59.50

     </details>
    <br>

## Conclusions

Coloque aqui las conclusiones...

### Criterios de evaluación

- [x] Despligue de los resultados y analisis claro de los resultados respecto a lo visto en la teoria.
- [x] Creatividad y orden.
- [x] Sección con las conclusiones de los experimentos realizados.
