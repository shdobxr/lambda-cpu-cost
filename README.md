# lambda-cpu-cost
Test harness that invokes cpu-intensive Lambda functions at various memory levels and compares performance and cost.
## What is it?
This is a test harness that invokes a CPU-bound Lambda function concurrently so that execution time and cost can be measured. The maximum concurrency is configurable so that the function can be executed many times in parallel without causing AWS to throttle it.
## Sieve of Eratosthenes
The Labmda function implements the Sieve of Eratosthenes algorithm for calculating prime numbers.  All prime numbers less than or equal to n are calculated, where n is configurable.  The Sieve consumes memory and the function will loop a configurable number of times to accumulate CPU usage within a constrained memory footprint.  The execution time is mesaured by the function and output to the test harness.

Multiple variants of the function are supported so that the performance of various Lambda memory settings can be compared with each other. The smallest Lambda memory setting is 128MB.  By default, four functions are defined: 128MB, 256MB, 512MB and 1024MB.  Every time the memory size doubles, Lambda provides double the CPU, making it straight forward to compare the execution time for calculating prime numbers across various memory settings.
