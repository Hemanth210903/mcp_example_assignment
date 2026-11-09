# MCP Assignment Answers

1\. How many tools were available in Part 1 and Part 3? What change was needed to make the new tool appear?

In Part 1, the MCP server provided 8 tools. In Part 3, it also provided 8 tools. I added a new tool called `predict_both` to the `mcp_ml_server.py` file. This tool runs both Logistic Regression and KNN models and compares their predictions. I also created a separate client file called `my_client.py` to call the new tool. The new tool appeared when I ran the updated client. It replaced the `export_parquet_audit` tool in the displayed tool list, so the total number of tools remained 8.

2\. How many of the 114 patients had different predictions from the two models?

The two models disagreed on 8 out of 114 test patients. The disagreements were:

- Patient 3: Actual class was benign. Logistic Regression predicted benign, while KNN predicted malignant. Logistic Regression was correct.
- Patient 25: Actual class was benign. Logistic Regression predicted benign, while KNN predicted malignant. Logistic Regression was correct.
- Patient 48: Actual class was benign. Logistic Regression predicted benign, while KNN predicted malignant. Logistic Regression was correct.
- Patient 53: Actual class was malignant. Logistic Regression predicted benign, while KNN predicted malignant. KNN was correct.
- Patient 76: Actual class was malignant. Logistic Regression predicted malignant, while KNN predicted benign. Logistic Regression was correct.
- Patient 80: Actual class was benign. Logistic Regression predicted benign, while KNN predicted malignant. Logistic Regression was correct.
- Patient 99: Actual class was benign. Logistic Regression predicted benign, while KNN predicted malignant. Logistic Regression was correct.
- Patient 102: Actual class was malignant. Logistic Regression predicted malignant, while KNN predicted benign. Logistic Regression was correct.

3\. Which model was correct more often when the two models disagreed?

Logistic Regression was correct more often when the two models disagreed. It correctly predicted 7 out of the 8 patients, while KNN correctly predicted only 1 patient. Based on these disagreement cases, Logistic Regression performed better than KNN.

4\. Why is the triple-quoted description important when creating an MCP tool?

The triple-quoted description explains what the tool does. It helps the AI client understand the purpose of the tool and when it should be used. A clear description makes it easier for the AI to select the correct tool for a particular request. Without a proper description, the AI may misunderstand the tool's purpose or choose the wrong tool.

5\. Why is the audit log useful?

The audit log is useful because it records the tool calls made by the client. It stores information such as the request ID, tool name, and execution status. This helps track which tools were executed and whether they completed successfully. It is also useful for debugging errors, checking the execution history, and verifying that the MCP tools worked correctly. In this assignment, the audit log showed successful calls for `get_sample_input` and `predict_both` across the test patients.