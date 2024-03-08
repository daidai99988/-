# -
单词计数器
import re
from collections import Counter

def count_words(filename):
    # 读取文本文件内容
    with open(filename, 'r') as file:
        text = file.read()

    # 使用正则表达式匹配单词
    words = re.findall(r'\b\w+\b', text.lower())

    # 统计单词出现次数
    word_count = Counter(words)

    return word_count

def main():
    filename = input("Enter the filename: ")
    word_count = count_words(filename)

    print("Word count:")
    for word, count in word_count.most_common():
        print(f"{word}: {count}")

if __name__ == "__main__":
    main()
