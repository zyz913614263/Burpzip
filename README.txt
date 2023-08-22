pyhton 实现暴力破解zip文件密码


运行环境 Python 3.9.13
pip install pyzipper

效率有点慢 3位数字需要 1.58s


原理就是枚举密码，尝试调用解压，返回密码是否正确

with pyzipper.AESZipFile(self.file, 'r', compression=pyzipper.ZIP_DEFLATED, encryption=pyzipper.WZ_AES) as extracted_zip:
            extracted_zip.extractall(pwd=str.encode(pwd))
            return pwd

破成功会打印解压密码。
可以用密码去用解压工具解压。
