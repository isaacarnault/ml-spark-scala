This is the part of the gist, we'll use some `Machine Learning` algorithms using `Spark - Scala`.<br>

Why use `Machine Learning` ?<br>

Here are common Uses Cases related to `Machine Learning`:<br>
- Fraud detection<br>
- Web engines<br>
- Credit scoring<br>
- Prediction of equipment failures<br>
- Customer segmentation<br>
- Customer churn prediction<br><br>
- Image regognition<br>
- Financial forecasts<br>

<b>Machine Learning steps</b><br>
1. Data acquisition / ingestion > 2. Data cleaning / transform > 3. Data testing <br>
4. Model training / building > 4. Model testing > 5. Model deployment<br>
<b>Machine Learning types</b><br>
1. Supervised learning, from labeled data<br>
2. Unsupervised learning, from unlabed data<br>
3. Reinforcement learning, from experience on data<br>

<b>Machine Learning APIs</b>
. Spark has 2 ML ApIs<br>
1. `RDD` API<br>
2. `Dataframe` API

<b>Data Raw operations</b><br>

Before defining  a model to use in `ML`, make sure you follow the 3 following steps:<br>
1. Extraction: selecting the pertinent variables<br>
2. Transformation: scaling, converting, preparing the dataframe<br>
3. Selection: select the correct model

<b>Metrics to consider for evaluating ML models</b>
[![metrics.png](https://i.postimg.cc/BZg1FMB0/metrics.png)](https://postimg.cc/rzDmXGHn)

<hr>

#### Working environment - Install IntelliJ
Go to https://www.jetbrains.com/idea/download/#section=linux and download <b>Community</b> edition.<br>

<details>
<summary>🔴 See hint</summary>
<p> 
  
[![intelliJ.png](https://i.postimg.cc/4dJY0GN3/intelliJ.png)](https://postimg.cc/B8VZ8dFW)

</p>
</details>

2. Extract the soft from the tarball (.tgz) and start the application from the bin repository.

<details>
<summary>🔴 See hint</summary>
<p> 
  
[![isaac-arnault-intelli-J.png](https://i.postimg.cc/rm6Byyt8/isaac-arnault-intelli-J.png)](https://postimg.cc/R3RsXBR8)

</p>
</details>

3. Go to configure > Plugins > From the Marketplace, install `Scala`.

<details>
<summary>🔴 See hint</summary>
<p> 
  
[![isaac-arnault-intelli-J-2.png](https://i.postimg.cc/DyBmSH6V/isaac-arnault-intelli-J-2.png)](https://postimg.cc/bsSqM64L)

</p>
</details>

4. Restard `IntelliJ` to apply changes.<br>

<details>
<summary>🔴 See hint</summary>
<p> 
  
[![isaac-arnault-intelli-J-3.png](https://i.postimg.cc/JzMg2dCh/isaac-arnault-intelli-J-3.png)](https://postimg.cc/BX7M8p6W)

</p>
</details>

5. Create New Project > Select "Scala" and Next > Name: ML_Spark_Scala<br>
> Location: create a folder named "Projects" in the `IntelliJ` repository and set location to that folder.

<details>
<summary>🔴 See hint</summary>
<p> 
  
[![isaac-arnault-intelli-J-6.png](https://i.postimg.cc/LXtLwvpH/isaac-arnault-intelli-J-6.png)](https://postimg.cc/jwjDJH29)

</p>
</details>

6. Click "Finish" to apply configs and create your first project.

<details>
<summary>🔴 See hint</summary>
<p> 
  
[![isaac-arnault-Intelli-J-7.png](https://i.postimg.cc/9FMwYcrX/isaac-arnault-Intelli-J-7.png)](https://postimg.cc/nMyLHb4N)

</p>
</details>

Now we are ready to start using `IntelliJ`.

## A. Regression - Linear regression
We will apply a linear regression script on a given dataset <b>sample_linear_regression_data.txt</b>
1. Check <b>datasets.md</b> section of this gist to download the dataset and save it to a folder on your desktop.<br>
2. In `IntelliJ`, open the .txt file to have a quick view on the data.<br>
3. Save the below program in your Desktop as `LinReg.scala`.<br>

<details>
<summary>🔴 LinReg.scala </summary>
<p>
  
 ``` 
import org.apache.spark.ml.regression.LinearRegression
import org.apache.spark.sql.SparkSession

def main(): Unit = {
  // Create Session App
  val spark = SparkSession.builder().appName("LinearRegressionExample").getOrCreate()

  // May need to replace with full file path starting with file:///.
  val path = "url-path/sample_linear_regression_data.txt"

  // Training Data
  val training = spark.read.format("libsvm").load(path)
  training.printSchema()

  // Create new LinearRegression Object
  val lr = new LinearRegression().setMaxIter(100).setRegParam(0.3).setElasticNetParam(0.8)

  // Fit the model
  val lrModel = lr.fit(training)

  // Print the coefficients and intercept for linear regression
  println(s"Coefficients: ${lrModel.coefficients} Intercept: ${lrModel.intercept}")

  // Summarize the model over the training set and print out some metrics
  val trainingSummary = lrModel.summary
  println(s"numIterations: ${trainingSummary.totalIterations}")
  println(s"objectiveHistory: ${trainingSummary.objectiveHistory.toList}")
  trainingSummary.residuals.show()
  println(s"RMSE: ${trainingSummary.rootMeanSquaredError}")
  println(s"r2: ${trainingSummary.r2}")

  // $example off$
  spark.stop()
}
main()

```

</p>
</details>

4. Open a Terminal window in `IntelliJ` and start `Spark` using `$ ./spark-shell`.<br>

<details>
<summary>🔴 See on IntelliJ</summary>
<p> 
  
[![isaac-arnault-spark-scala.png](https://i.postimg.cc/0QGPLXy2/isaac-arnault-spark-scala.png)](https://postimg.cc/phdwjZjg)

</p>
</details>

6. Once `Spark` has started, load the above program using `> :load url-path/LinRegDocExample.scala`.<br>

<details>
<summary>🔴 See on IntelliJ</summary>
<p> 
  
[![isaac-arnault-spark-scala.png](https://i.postimg.cc/0QGPLXy2/isaac-arnault-spark-scala.png)](https://postimg.cc/phdwjZjg)

</p>
</details>

<b>Program output</b>

<details>
<summary>🔴 See on IntelliJ</summary>
<p> 
  
[![isaac-arnault-intelli-J-7.png](https://i.postimg.cc/SswqY01r/isaac-arnault-intelli-J-7.png)](https://postimg.cc/JDcSSFLD)

</p>
</details>

<b>RSME</b> Root Mean Square Error. It represents the sample standard deviation of the differences between predicted values and observed values (called residuals).<br>

[![RSME.png](https://i.postimg.cc/CxZZWYTh/RSME.png)](https://postimg.cc/yDHYZM8t)

<b>r2</b> r-square, usually between 0 and 1, here 0.02 which is a poor score. The higher the score is, the better the model is.

[![r.png](https://i.postimg.cc/GpG4mQm6/r.png)](https://postimg.cc/CZMhvbD4)

</details>
