#policy evaluation

The following operations can be performed on "policy evaluation":


##show policy evaluation

Executes pixl expression or action and gives result. Result type can be zero or more of:-Bool-Num-Double-Unsigned long-String


##Synopsys

show policy evaluation (-expression &lt;expression> | -action &lt;string>) -type &lt;type> -input &lt;string>


##Arguments

<b>expression</b>
Expression string. For example: http.req.body(100).contains("this").

<b>action</b>
Rewrite action name. Supported rewrite action types are:
-delete
-delete_all
-delete_http_header
-insert_after
-insert_after_all
-insert_before
-insert_before_all
-insert_http_header
-replace
-replace_all

<b>type</b>
Indicates request or response input packet
Possible values: HTTP_REQ, HTTP_RES, TEXT

<b>input</b>
Text representation of input packet.



##Outputs

<b>stateflag</b>

<b>pitModifiedInputData</b>
Text representation of packet after evaluating expression or rewrite action.

<b>pitBoolResult</b>
Result of the expression in bool format.

<b>pitNumResult</b>
Result of the expression in num format.

<b>pitDoubleResult</b>
Result of the expression in double format.

<b>pitUlongResult</b>
Result of the expression in unsigned long format.

<b>pitRefResult</b>
Result of the expression in string format.

<b>isPitEmptyRefResult</b>
Result of the expression is empty string.

<b>pitOffsetResult</b>
Offset of the resultant sting.

<b>pitOffsetResultLen</b>
Offset length of the resultant sting.

<b>isTruncatedRefResult</b>
Identify whether ref result is truncated result.

<b>pitBoolEvalTime</b>
Average evaluation time of bool type expression in nanoseconds.

<b>pitNumEvalTime</b>
Average evaluation time of num type expression in nanoseconds.

<b>pitDoubleEvalTime</b>
Average evaluation time of double type expression in nanoseconds.

<b>pitUlongEvalTime</b>
Average evaluation time of unsigned long type expression in nanoseconds.

<b>pitRefEvalTime</b>
Average evaluation time of string type expression in nanoseconds.

<b>pitOffsetEvalTime</b>
Average evaluation time in finding offset of the resultant string in the input. Time is in nanoseconds.

<b>pitActionEvalTime</b>
Average evaluation time of rewrite action in nanoseconds.

<b>pitOperationPerformerArray</b>
Details of the operation NS performed at various offsets during applying of rewrite action on input data. Operation can be insertion, modfication or deletion.

<b>pitOldOffsetArray</b>
Details of the offsets in the input data at which NS either inserted or modified or deleted data during applying of rewrite action.

<b>pitNewOffsetArray</b>
Details of the offsets in the output data at which NS either inserted or modified or deleted data during applying of rewrite action.

<b>pitOffsetLengthArray</b>
Details of the lengths of the data which NS either inserted or modified or deleted during applying of rewrite action.

<b>pitBoolErrorResult</b>
Result of the bool type expression if any error occurs during evaluation. Result will be in string format.

<b>pitNumErrorResult</b>
Result of the num type expression if any error occurs during evaluation. Result will be in string format.

<b>pitDoubleErrorResult</b>
Result of the double type expression if any error occurs during evaluation. Result will be in string format.

<b>pitUlongErrorResult</b>
Result of the unsigned long type expression if any error occurs during evaluation. Result will be in string format.

<b>pitRefErrorResult</b>
Result of the ref type expression if any error occurs during evaluation. Result will be in string format.

<b>pitOffsetErrorResult</b>
Result of the expression if any error occurs in calculating offset. Result will be in string format.

<b>pitActionErrorResult</b>
Result of the action if any error occurs in evaluation. Result will be in string format.

<b>devno</b>

<b>count</b>



##Example

Example 1: show policy evaluation -action rw_act_1 -type http_req -input 'GET / HTTP/1.1\\\\r\\\\nHost: abc.com\\\\r\\\\n\\\\r\\\\n'Example 2: show policy evaluation -expression 'http.res.body(10).contains("foo")' -type http_res -input "HTTP/1.1 200 OK\\\\r\\\\n\\\\r\\\\nabcdfooabcd"Example 3: show policy evaluation -expression 'text.contains("foo")' -type text -input "testing_test_foo"

