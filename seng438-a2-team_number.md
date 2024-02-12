**SENG 438 - Software Testing, Reliability, and Quality**

**Lab. Report \#2 – Requirements-Based Test Generation**

| Group \#:      |     |
| -------------- | --- |
| Student Names: |     |
|                |     |
|                |     |
|                |     |

# 1 Introduction

The goal of this lab is to understand the basics of unit testing. This is achieved by focusing on the basic requirements for each unit or method. We will be using Junit in order to test our Java methods to ensure their functionality. The System Under Test (SUT) is JFreeChart and it houses all the classes which we will be testing by utilizing junit. The initial part of this lab will focus on the setup of eclipse, then we will be creating dedicated unit tests for each method based on the requirements found in the javadocs, finally running the tests and collecting the results.  

Before the Lab, we were not aware of JFreeChart and its utilizations, however we did have a basic understanding of how to utilize Junit in order to create effective and helpful test cases.

By doing this lab, we will be practicing the notions of black box testing as we did not have access to the code, boundary value analysis and equivalence classes. These three are instrumental parts of writing effective Junit test cases. 

# 2 Detailed description of unit test strategy

**Input Partitions for Range: **



1. getLength() Method

The inputs were partitioned into equivalence classes. The inputs could be positive or negative numbers, or 0. Test cases were written to test these equivalence classes against their expected behaviour. All of the inputs provided to the test method were valid (i.e. a validly constructed Range object)

The following ranges of inputs were tested:



1. Range between positive upper and lower bounds
2. Range between positive upper bound and negative lower bound
3. Range between negative upper and lower bounds
4. Range between an equal bounded range (i.e. both the upper and lower bounds are the same)
5. Range between a 0 lower bound and a positive upper bound
6. Range between a negative lower bound and a 0 upper bound
2. getCentralValue() Method

The inputs were partitioned into equivalence classes. The inputs could be positive or negative numbers, or 0. Test cases were written to test these equivalence classes against their expected behaviour. All of the inputs provided to the test method were valid (i.e. a validly constructed Range object)

The following ranges of inputs were tested:



1. Range between positive upper and lower bounds
2. Range between positive upper bound and negative lower bound
3. Range between negative upper and lower bounds
4. Range between an equal bounded range (i.e. both the upper and lower bounds are the same)
5. Range between a 0 lower bound and a positive upper bound
6. Range between a negative lower bound and a 0 upper bound
3. constrain(double) Method

The inputs were partitioned into equivalence classes. The input could either be less than the lower bound of the range, within the range, or greater than the upper bound of the range. Test cases were written to test these equivalence classes against their expected behaviour. The boundary conditions of the behaviour at the upper and lower bounds were also tested.  All of the inputs provided to the test method were valid (i.e. a validly constructed Range object)

The following inputs were tested against a range of -1 to 1:



1. Value in the range
2. Value equal to the lower bound
3. Value equal to the upper bound
4. Value less than the lower bound 
5. Value greater than the upper bound
4. contains(double) Method

The inputs were partitioned into equivalence classes. The input could either be less than the lower bound of the range, within the range, or greater than the upper bound of the range. Test cases were written to test these equivalence classes against their expected behaviour. The boundary conditions of the behaviour at the upper and lower bounds were also tested.  All of the inputs provided to the test method were valid (i.e. a validly constructed Range object)

The following inputs were tested against a range of -1 to 1:



1. Value in the range
2. Value equal to the lower bound
3. Value equal to the upper bound
4. Value less than the lower bound
5.  Value greater than the upper bound
5. intersects(double lowerbound, double upperbound) Method

The inputs were partitioned into equivalence classes. The input range could either be less than the lower bound of the range, within the range, overlapping with the range or greater than the upper bound of the range. Test cases were written to test these equivalence classes against their expected behaviour. The boundary conditions of the behaviour at the upper and lower bounds were also tested by testing an input range equal to the range, and input ranges with one bound equal to the upper or lower bound. The condition of a 0 length range both in the range and out of it was also tested. The method was also tested with invalid inputs (i.e. the lower bound greater than upper bound) when the provided numbers were in range and when they were not. 

The following input ranges were tested with the range -1 to 1: 



1. Range less than the lower bound 
2. Range that intersects over the lower bound 
3. Range fully within the range
4. Range that intersects over the upper bound
5. Range equivalent to the original range
6. Range greater than the upper bound 
7. Range that only intersects at the lower bound 
8. Range that only intersects at the upper bound 
9. Range that intersects with 0 length (i.e. equivalent upper and lower bounds)
10. Range that does not intersect with 0 length (i.e. equivalent upper and lower bounds)
11. Invalidly entered range that is not in range (if the numbers were entered correctly)
12. Invalidly entered range that is in range (if the numbers were entered correctly)

**Input partitions for DataUtilities**

To reliably test the DataUtilities class we will first look at the input parameters to the methods and the method signature to create tables showing the valid and invalid equivalent classes for the inputs to these variables. From these tables we will be able to clearly visualise what test cases need to be provided for each method.


1. calculateColumnTotal:


### Values2D data


<table>
  <tr>
   <td>Partition
   </td>
   <td>Value
   </td>
  </tr>
  <tr>
   <td>1
   </td>
   <td>Valid Values2D object
   </td>
  </tr>
  <tr>
   <td>2
   </td>
   <td>null
   </td>
  </tr>
</table>



### int column


<table>
  <tr>
   <td>Partition
   </td>
   <td>Value
   </td>
  </tr>
  <tr>
   <td>3
   </td>
   <td>Valid column index containing integers
   </td>
  </tr>
  <tr>
   <td>4
   </td>
   <td>Valid column index containing null values
   </td>
  </tr>
  <tr>
   <td>5
   </td>
   <td>Invalid column index below bounds (&lt; 0)
   </td>
  </tr>
  <tr>
   <td>6
   </td>
   <td>Invalid column index above bounds (> data.getRowCound())
   </td>
  </tr>
</table>



## 2.calculateRowTotal:


### Values2D data


<table>
  <tr>
   <td>Partition
   </td>
   <td>Value
   </td>
  </tr>
  <tr>
   <td>1
   </td>
   <td>Valid Values2D object
   </td>
  </tr>
  <tr>
   <td>2
   </td>
   <td>null
   </td>
  </tr>
</table>



### int row


<table>
  <tr>
   <td>Partition
   </td>
   <td>Value
   </td>
  </tr>
  <tr>
   <td>3
   </td>
   <td>Valid row index containing all integers
   </td>
  </tr>
  <tr>
   <td>4
   </td>
   <td>Valid row index containing number and null values
   </td>
  </tr>
  <tr>
   <td>5
   </td>
   <td>Invalid row index below bounds (&lt; 0)
   </td>
  </tr>
  <tr>
   <td>6
   </td>
   <td>Invalid row index above bounds (> data.getRowCound())
   </td>
  </tr>
</table>



## 3.createNumberArray


### double[ ] data


<table>
  <tr>
   <td>Partition
   </td>
   <td>Value
   </td>
  </tr>
  <tr>
   <td>1
   </td>
   <td>Valid array of doubles
   </td>
  </tr>
  <tr>
   <td>2
   </td>
   <td>Empty double array
   </td>
  </tr>
  <tr>
   <td>3
   </td>
   <td>Large Array
   </td>
  </tr>
  <tr>
   <td>4
   </td>
   <td>Null
   </td>
  </tr>
</table>



## 4.createNumberArray2D


### double[ ][ ] data


<table>
  <tr>
   <td>Partition
   </td>
   <td>Value
   </td>
  </tr>
  <tr>
   <td>1
   </td>
   <td>Valid array of double arrays
   </td>
  </tr>
  <tr>
   <td>2
   </td>
   <td>Empty Array
   </td>
  </tr>
  <tr>
   <td>3
   </td>
   <td>Large Array
   </td>
  </tr>
  <tr>
   <td>4
   </td>
   <td>Null
   </td>
  </tr>
</table>



## 5.getCumulativePercentages


### KeyedValues data


<table>
  <tr>
   <td>Partition
   </td>
   <td>Value
   </td>
  </tr>
  <tr>
   <td>1
   </td>
   <td>(key, value) = (int, int)
   </td>
  </tr>
  <tr>
   <td>2
   </td>
   <td>(key, value) = (double, int)
   </td>
  </tr>
  <tr>
   <td>3
   </td>
   <td>(key, value) = (int, double)
   </td>
  </tr>
  <tr>
   <td>4
   </td>
   <td>(key, value) = (letter, int)
   </td>
  </tr>
  <tr>
   <td>5
   </td>
   <td>Key with a negative value associated with it
   </td>
  </tr>
  <tr>
   <td>6
   </td>
   <td>Key with a null value associated with it
   </td>
  </tr>
  <tr>
   <td>7
   </td>
   <td>A key with a very large value associated, and another with a very small value
   </td>
  </tr>
  <tr>
   <td>8
   </td>
   <td>Null 
   </td>
  </tr>
  <tr>
   <td>9
   </td>
   <td>Single value 
   </td>
  </tr>
</table>


# 3 Test cases developed

Range:


<table>
  <tr>
   <td><strong>Method Tested</strong>
   </td>
   <td><strong>Test Name</strong>
   </td>
   <td><strong>Input Partition Tested</strong>
   </td>
  </tr>
  <tr>
   <td>getLength()
   </td>
   <td>testGetLengthPositiveBounds() 
   </td>
   <td>1a
   </td>
  </tr>
  <tr>
   <td>getLength()
   </td>
   <td>testGetLengthPositiveAndNegativeBounds()
   </td>
   <td>1b
   </td>
  </tr>
  <tr>
   <td>getLength()
   </td>
   <td>testGetLengthNegativeBounds()
   </td>
   <td>1c
   </td>
  </tr>
  <tr>
   <td>getLength()
   </td>
   <td>testGetLengthEqualBounds()
   </td>
   <td>1d
   </td>
  </tr>
  <tr>
   <td>getLength()
   </td>
   <td>testGetLengthZeroLowerBoundPositiveUpperBound()
   </td>
   <td>1e
   </td>
  </tr>
  <tr>
   <td>getLength()
   </td>
   <td>testGetLengthNegativeLowerBoundZeroUpperBound()
   </td>
   <td>1f
   </td>
  </tr>
  <tr>
   <td>getCentralValue()
   </td>
   <td>testGetCentralValuePositiveBounds()
   </td>
   <td>2a
   </td>
  </tr>
  <tr>
   <td>getCentralValue()
   </td>
   <td>testGetCentralValueNegativeBounds()
   </td>
   <td>2c
   </td>
  </tr>
  <tr>
   <td>getCentralValue()
   </td>
   <td>testGetCentralValuePositiveAndNegativeBounds()
   </td>
   <td>2b
   </td>
  </tr>
  <tr>
   <td>getCentralValue()
   </td>
   <td>testGetCentralValueEqualBounds()
   </td>
   <td>2d
   </td>
  </tr>
  <tr>
   <td>getCentralValue()
   </td>
   <td>testGetCentralValueZeroLowerBoundPositiveUpperBound()
   </td>
   <td>2e
   </td>
  </tr>
  <tr>
   <td>getCentralValue()
   </td>
   <td>testGetCentralValueNegativeLowerBoundZeroUpperBound()
   </td>
   <td>2f
   </td>
  </tr>
  <tr>
   <td>constrain()
   </td>
   <td>testConstrainValueInRange()
   </td>
   <td>3a
   </td>
  </tr>
  <tr>
   <td>constrain()
   </td>
   <td>testConstrainValueAtLowerBound()
   </td>
   <td>3b
   </td>
  </tr>
  <tr>
   <td>constrain()
   </td>
   <td>testConstrainValueAtUpperBound()
   </td>
   <td>3c
   </td>
  </tr>
  <tr>
   <td>constrain()
   </td>
   <td>testConstrainValueLessThanLowerBound()
   </td>
   <td>3d
   </td>
  </tr>
  <tr>
   <td>constrain()
   </td>
   <td>testConstrainValueGreaterThanUpperBound()
   </td>
   <td>3e
   </td>
  </tr>
  <tr>
   <td>contains()
   </td>
   <td>testContainsValueInRange()
   </td>
   <td>4a
   </td>
  </tr>
  <tr>
   <td>contains()
   </td>
   <td>testContainsValueLessThanLowerBound() 
   </td>
   <td>4d
   </td>
  </tr>
  <tr>
   <td>contains()
   </td>
   <td>testContainsValueAtLowerBound()
   </td>
   <td>4b
   </td>
  </tr>
  <tr>
   <td>contains()
   </td>
   <td>testContainsValueAtUpperBound()
   </td>
   <td>4c
   </td>
  </tr>
  <tr>
   <td>contains()
   </td>
   <td>testContainsValueGreaterThanUpperBound()
   </td>
   <td>4e
   </td>
  </tr>
  <tr>
   <td>intersects()
   </td>
   <td>testIntersectsRangeLessThanLowerBound()
   </td>
   <td>5a
   </td>
  </tr>
  <tr>
   <td>intersects()
   </td>
   <td>testIntersectsRangeIntersectsOverLowerBound()
   </td>
   <td>5b
   </td>
  </tr>
  <tr>
   <td>intersects()
   </td>
   <td>testIntersectsRangeIntersectsRange()
   </td>
   <td>5c
   </td>
  </tr>
  <tr>
   <td>intersects()
   </td>
   <td>testIntersectsRangeIntersectsOverUpperBound()
   </td>
   <td>5d
   </td>
  </tr>
  <tr>
   <td>intersects()
   </td>
   <td>testIntersectsRangeIntersectsOverEntireRange()
   </td>
   <td>5e
   </td>
  </tr>
  <tr>
   <td>intersects()
   </td>
   <td>testIntersectsRangeGreaterThanUpperBound()
   </td>
   <td>5f
   </td>
  </tr>
  <tr>
   <td>intersects()
   </td>
   <td>testIntersectsRangeIntersectsAtLowerBound()
   </td>
   <td>5g
   </td>
  </tr>
  <tr>
   <td>intersects()
   </td>
   <td>testIntersectsRangeIntersectsAtUpperBound()
   </td>
   <td>5h
   </td>
  </tr>
  <tr>
   <td>intersects()
   </td>
   <td>testIntersectsRangeIntersectsWithZeroLength() 
   </td>
   <td>5i
   </td>
  </tr>
  <tr>
   <td>intersects()
   </td>
   <td>testIntersectsRangeNotInRangeWithZeroLength() 
   </td>
   <td>5j
   </td>
  </tr>
  <tr>
   <td>intersects()
   </td>
   <td>testIntersectsInvalidInputNotInRange()
   </td>
   <td>5k
   </td>
  </tr>
  <tr>
   <td>intersects()
   </td>
   <td>testIntersectsInvalidInputInRange()
   </td>
   <td>5l
   </td>
  </tr>
</table>


DataUtilities:


<table>
  <tr>
   <td><strong>Method Tested</strong>
   </td>
   <td><strong>Test Name</strong>
   </td>
   <td><strong>Input Partition Tested</strong>
   </td>
  </tr>
  <tr>
   <td>calculateColumnTotal
   </td>
   <td>calculateColumnTotalForColumnWithAllNumbers
   </td>
   <td>1.3
   </td>
  </tr>
  <tr>
   <td>calculateColumnTotal
   </td>
   <td>calculateColumnTotalForColumnWithNumbersAndNull
   </td>
   <td>1.4
   </td>
  </tr>
  <tr>
   <td>calculateColumnTotal
   </td>
   <td>calculateColumnTotalForColumnWithAllNull
   </td>
   <td>1.2
   </td>
  </tr>
  <tr>
   <td>calculateColumnTotal
   </td>
   <td>calculateColumnTotalForColumnAboveRange
   </td>
   <td>1.6
   </td>
  </tr>
  <tr>
   <td>calculateColumnTotal
   </td>
   <td>calculateColumnTotalForColumnBelowRange
   </td>
   <td>1.5
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
   </td>
   <td>
   </td>
  </tr>
  <tr>
   <td>calculateRowTotal
   </td>
   <td>calculateRowTotalForRowWithAllNumbers
   </td>
   <td>2.3
   </td>
  </tr>
  <tr>
   <td>calculateRowTotal
   </td>
   <td>calculateRowTotalForRowWithNumbersAndNull
   </td>
   <td>2.4
   </td>
  </tr>
  <tr>
   <td>calculateRowTotal
   </td>
   <td>calculateRowTotalForRowWithAllNull
   </td>
   <td>2.2
   </td>
  </tr>
  <tr>
   <td>calculateRowTotal
   </td>
   <td>calculateRowTotalForRowAboveRange
   </td>
   <td>2.6
   </td>
  </tr>
  <tr>
   <td>calculateRowTotal
   </td>
   <td>calculateRowTotalForRowBelowRange
   </td>
   <td>2.5
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
   </td>
   <td>
   </td>
  </tr>
  <tr>
   <td>createNumberArray
   </td>
   <td>createNumberArrayWithDoublesOnly
   </td>
   <td>3.1
   </td>
  </tr>
  <tr>
   <td>createNumberArray
   </td>
   <td>createNumberArrayWithEmptyArray
   </td>
   <td>3.2
   </td>
  </tr>
  <tr>
   <td>createNumberArray
   </td>
   <td>createNumberArrayWithLargeArray
   </td>
   <td>3.3
   </td>
  </tr>
  <tr>
   <td>createNumberArray
   </td>
   <td>createNumberArrayForInvalidInput
   </td>
   <td>3.4
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
   </td>
   <td>
   </td>
  </tr>
  <tr>
   <td>createNumberArray2D
   </td>
   <td>createNumberArray2DWithDoublesOnly
   </td>
   <td>4.1
   </td>
  </tr>
  <tr>
   <td>createNumberArray2D
   </td>
   <td>createNumberArray2DWithEmptyArray
   </td>
   <td>4.2
   </td>
  </tr>
  <tr>
   <td>createNumberArray2D
   </td>
   <td>createNumberArray2DWithLargeArray
   </td>
   <td>4.3
   </td>
  </tr>
  <tr>
   <td>createNumberArray2D
   </td>
   <td>createNumberArray2DForInvalidInput
   </td>
   <td>4.4
   </td>
  </tr>
  <tr>
   <td>
   </td>
   <td>
   </td>
   <td>
   </td>
  </tr>
  <tr>
   <td>getCumulativePercentages
   </td>
   <td>getCumulativePercentagesForSingleValue
   </td>
   <td>5.9
   </td>
  </tr>
  <tr>
   <td>getCumulativePercentages
   </td>
   <td>getCumulativePercentagesForInt
   </td>
   <td>5.1
   </td>
  </tr>
  <tr>
   <td>getCumulativePercentages
   </td>
   <td>getCumulativePercentagesDoubleInt
   </td>
   <td>5.2
   </td>
  </tr>
  <tr>
   <td>getCumulativePercentages
   </td>
   <td>getCumulativePercentagesForIntDouble
   </td>
   <td>5.3
   </td>
  </tr>
  <tr>
   <td>getCumulativePercentages
   </td>
   <td>getCumulativePercentagesForCharInt
   </td>
   <td>5,4
   </td>
  </tr>
  <tr>
   <td>getCumulativePercentages
   </td>
   <td>getCumulativePercentagesForNegativeKey
   </td>
   <td>5.5
   </td>
  </tr>
  <tr>
   <td>getCumulativePercentages
   </td>
   <td>getCumulativePercentagesForLargeValues
   </td>
   <td>5.7
   </td>
  </tr>
  <tr>
   <td>getCumulativePercentages
   </td>
   <td>getCumulativePercentagesWithEmptyInput
   </td>
   <td>5.6
   </td>
  </tr>
  <tr>
   <td>getCumulativePercentages
   </td>
   <td>getCumulativePercentagesWithNullInput
   </td>
   <td>5.<em>8</em>
   </td>
  </tr>
</table>


# 4 How the team work/effort was divided and managed

The team work was divided equally among all four group members. We decided it was best to split up into two teams of two who would pair program together during our lab session (i.e. one team took Range and the other took DataUtilities). As a pair, each team created their plans and associated partitions. Once done, we started creating the tests and were able to switch drivers and passengers ensuring everyone had a go at creating Junit tests. After the tests were complete, we all worked to put the information together to create this lab report. 

# 5 Difficulties encountered, challenges overcome, and lessons learned

Some difficulties encountered were navigating the intricate file system that was given to us which composed all the Jar files, as well as the javadocs. The file hierarchy was initially very intimidating but after some familiarization we were able to understand it and find what we needed. Another difficulty was understanding how to properly utilize mocks, we consulted with a TA which helped us move forward with utilizing them. An initial hurdle was navigating the eclipse as we have all never used it before. For the most part we have completed java development in Intellij so trying to find everything in eclipse took some getting used to. Some lessons learned were that testing is quite important and that Junit is a powerful resource to ensure proper functionality. We are now all more comfortable with creating, running, and understanding unit tests. 

# 6 Comments/feedback on the lab itself

The lab ReadMe instructions were actually very straightforward and helpful. It explained the eclipse download process quite well and was seriously very helpful. Also, the requirements of the assignment were made to be clear which permitted us to get started on it right away instead of pondering what we needed to do. Overall the lab was well designed, the only thing we would say which was annoying was not much info on how to properly utilise Mockery (supplement to the documentation). 

