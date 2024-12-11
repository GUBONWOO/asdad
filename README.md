# データベース設計

この文書は、データベーステーブルを説明する設計書です。

## ファイルテーブル設計

### テーブル: `file`

| カラム名              | 型         | 説明                   |
| --------------------- | ---------- | ---------------------- |
| `file_id`             | `int`      | ファイル固有 ID        |
| `thunder_name`        | `string`   | サンダーネーム         |
| `thunder_id`          | `string`   | サンダー ID            |
| `file_name`           | `string`   | ファイル名             |
| `file_type`           | `string`   | ファイルタイプ         |
| `file_group_id`       | `int`      | ファイルグループ ID    |
| `file_group_name`     | `string`   | ファイルグループ名     |
| `file_count`          | `int`      | ファイル数             |
| `trans_no`            | `int`      | トランザクション番号   |
| `file_order_list`     | `string`   | ファイルオーダーリスト |
| `thumbnail_data`      | `blob`     | サムネイルデータ       |
| `data`                | `blob`     | データ                 |
| `create_time`         | `datetime` | 作成時間               |
| `file_create_time`    | `datetime` | ファイル作成時間       |
| `ftp_port`            | `int`      | FTP ポート             |
| `ftp_user_id`         | `string`   | FTP ユーザー ID        |
| `message`             | `text`     | メッセージ             |
| `result`              | `string`   | 結果                   |
| `destination_number`  | `int`      | 目的地番号             |
| `destination_address` | `string`   | 目的地住所             |

---

## ファイルテーブル関係

```mermaid
classDiagram
    class file {
        +int file_id
        +string thunder_name
        +string thunder_id
        +string file_name
        +string file_type
        +int file_group_id
        +string file_group_name
        +int file_count
        +int trans_no
        +string file_order_list
        +blob thumbnail_data
        +blob data
        +datetime create_time
        +datetime file_create_time
        +int ftp_port
        +string ftp_user_id
        +text message
        +string result
        +int destination_number
        +string destination_address
    }

    class file_group {
        +int file_group_id
        +string file_group_name
    }

    file_group "1" -- "0..*" file : contains
```
