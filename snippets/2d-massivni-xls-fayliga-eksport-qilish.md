---
toc: false
title: "2D massivni xls fayliga eksport qilish."
description: "Microsoft excel uchun ma'lumotlarni eksport qilish."
keywords: "xls, array, export, excel"
---

```
function to_xls($data, $filename){
	$fp = fopen($filename, "w+");
	$str = pack(str_repeat("s", 6), 0x809, 0x8, 0x0, 0x10, 0x0, 0x0); 
	fwrite($fp, $str);
	if (is_array($data) && !empty($data)){
	    $row = 0;
	    foreach (array_values($data) as $_data){
	        if (is_array($_data) && !empty($_data)){
	            if ($row == 0){
	                foreach (array_keys($_data) as $col => $val){
	                    _xlsWriteCell($row, $col, $val, $fp);
	                }
	                $row++;
	            }
	            foreach (array_values($_data) as $col => $val){
	                _xlsWriteCell($row, $col, $val, $fp);
	            }
	            $row++;
	        }
	    }
	}
	$str = pack(str_repeat("s", 2), 0x0A, 0x00);
	fwrite($fp, $str);
	fclose($fp);
}

function _xlsWriteCell($row, $col, $val, $fp){
	if (is_float($val) || is_int($val)){
	    $str  = pack(str_repeat("s", 5), 0x203, 14, $row, $col, 0x0);
	    $str .= pack("d", $val);
	} else {
	    $l    = strlen($val);
	    $str  = pack(str_repeat("s", 6), 0x204, 8 + $l, $row, $col, 0x0, $l);
	    $str .= $val;
	}
	fwrite($fp, $str);
}
```

## Ishga tushirish

```
to_xls([
	[
		'id' => '1',
		'1-qator' => 'Test',
		'2-qator' => 'Test'
	],
	[
		'id' => '2',
		'1-qator' => 'Test',
		'2-qator' => 'Test'
	],
	[
		'id' => '3',
		'1-qator' => 'Test',
		'2-qator' => 'Test'
	]
], "export.xls");
```