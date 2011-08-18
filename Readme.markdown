# DKBenchmark

`DKBenchmark` is a utility class that makes it easy to benchmark code in Objective-C.

Results are logged via `NSLog`

It is used in the apps written by [Mostly Disco](http://www.mostlydisco.com)

## Installation

Copy the files into to your project folder, and add them to your Xcode project.

## Usage

To benchmark some code (with 100 iterations)

    NSString * someString = @"Greatest String Ever...";

    [DKBenchmark benchmark:@"Appending Strings" block:^{

      someString = [someString stringByAppendingString:@"...or is it?"];

    }];

If you want to specifiy the number of iterations:

    NSString * someString = @"It's over 9";

    [DKBenchmark benchmark:@"Appending Strings" iterations: 9001 block:^{

      someString = [someString stringByAppendingString:@"000"];

    }];

Running a benchmark will yield an output similar to the following:

    2011-08-18 14:33:31.483 YourApplication[3544:10707] [DKBenchmark] "Appending Strings" took 0.25 seconds on average with (100 iterations)

## How does it work?

It runs the code in the block you provide `x` times (default is 100). It
times how long each iteration of the block takes, and at the and, gives
you an average of all the numbers added together.

## Notes on benchmarking code

If you are writing an application for iPhone, be sure to test your code
on the actual device. Using the iPhone Simulator does not give you true
results as it uses your computers CPU to do the calculations. iOS
devices have a far less powerfull CPU.

## Note on Patches/Pull Requests

* Fork the project.
* Make your feature addition or bug fix.
* Send me a pull request. Bonus points for topic branches.

## Contributers

* [Keith Pitt](http://www.keithpitt.com)

## License

DKBenchmark is licensed under the MIT License:

  Copyright (c) 2011 Keith Pitt (http://www.keithpitt.com/)

  Permission is hereby granted, free of charge, to any person obtaining a copy
  of this software and associated documentation files (the "Software"), to deal
  in the Software without restriction, including without limitation the rights
  to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
  copies of the Software, and to permit persons to whom the Software is
  furnished to do so, subject to the following conditions:

  The above copyright notice and this permission notice shall be included in
  all copies or substantial portions of the Software.

  THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
  IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
  FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
  AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
  LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
  OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
  THE SOFTWARE.
