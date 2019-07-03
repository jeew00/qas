## Training file format
pandas DataFrame
| question_id | question | answer | paragraph | start_pos | end_pos | lang
| --- | --- | --- | --- | --- | --- | ---
| int | str | str | str | int | int | thai or eng (str)

Additional columns are fine but these columns are necessary

## Training example command

```
python3 run_thai_qa.py --bert_model bert-base-multilingual-cased \
--output_dir checkpoint/thai_only \
--do_train \
--train_file data/thai_train_3600.p
```

## Testing file format

pandas DataFrame
| question_id | question | answer | paragraph | lang
| --- | --- | --- | --- | ---
| int | str | str | str | thai or eng (str)

Additional columns are fine but these columns are necessary.

## Testing example command

```
python3 run_thai_qa.py --bert_model bert-base-multilingual-cased \
--output_dir path/to/output_result_dataframe/dir \
--do_predict --predict_file data/test_squad.p \
--checkpoint_dir checkpoint/thai_only \
--result_file path/to/output_result_dataframe.p
```
