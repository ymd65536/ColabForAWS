# Google ColabからAWSにアクセスしてみた

## AWS CLI のインストール

### 公式インストーラーを使用（推奨）

最新版のAWS CLI v2を公式インストーラーでインストールします。

```bash
# 1. インストーラーをダウンロード
! curl "https://awscli.amazonaws.com/awscli-exe-linux-$(uname -m).zip" -o "awscliv2.zip"

# 2. unzipがインストールされていない場合はインストール
! sudo apt update && sudo apt install unzip -y  # Ubuntu/Debian系
# または
! sudo yum install unzip -y                     # CentOS/RHEL系

# 3. ダウンロードしたファイルを展開
! unzip awscliv2.zip

# 4. インストール実行
! sudo ./aws/install

# 5. インストール確認
! aws --version

# ダウンロードしたzipファイルと展開したディレクトリを削除してクリーンアップします。
! rm  "awscliv2.zip"

# 解凍したディレクトリを削除
! rm -rf aws
```

## AWSにログイン

```bash
aws login
```

```bash
aws sts get-caller-identity
```

正常にログインできている場合、以下のような情報が表示されます：

```json
{
    "UserId": "AROAXXXXXXXXXXXXXX:username@company.com",
    "Account": "123456789012",
    "Arn": "arn:aws:sts::123456789012:assumed-role/RoleName/username@company.com"
}
```

## 参考リンク

- [AWS CLI ユーザーガイド](https://docs.aws.amazon.com/cli/latest/userguide/)
- [AWS SSO ユーザーガイド](https://docs.aws.amazon.com/singlesignon/latest/userguide/)
- [AWS CLI インストールガイド](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html)
