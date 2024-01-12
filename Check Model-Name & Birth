import re

def extract_all_beneficiaries(text):
    """
    Extracts all beneficiaries' names from the given text.

    Parameters:
    text (str): The text from which to extract the beneficiaries' names

    Returns:
    list: A list of extracted beneficiaries' names, or a message indicating none were found
    """
    # Regular expression to find all occurrences of beneficiaries
    beneficiary_pattern = r"Beneficiary:\s*(.*?)\s*(?=\n|$)"

    # Find all matches in the text
    beneficiaries_matches = re.findall(beneficiary_pattern, text)

    return beneficiaries_matches if beneficiaries_matches else ["No beneficiaries found"]


def extract_all_dob(text):

    dob_pattern = r"DOB:\s*(.*?)\s*(?=\n|$)"

    # Find all matches in the text
    dob_matches = re.findall(dob_pattern, text)

    return dob_matches if dob_matches else ["No dob found"]


# Example usage with multiple beneficiaries
# 复制 ListOfBeneficiares.html里面的文本内容粘贴到example_text这里
example_text = """

"""

text_a = extract_all_beneficiaries(example_text)
text_a_dob = extract_all_dob(example_text)

# 复制 0. Name List 中Name那一行到text_b
text_b = """

"""

text_b_list = [name for name in text_b.split('\n') if name]


text_b_adjusted = [' '.join(name.split(',')[::-1]).strip() for name in text_b_list]
text_b_adjusted

# 检查两个文本是否完全匹配
are_texts_matching_name = set(text_a) == set(text_b_adjusted)
are_texts_matching_name

# 复制 0. Name List 中Date of Birth mm-dd-yyyy那一行到dates_string
dates_string = '''

'''

# 将字符串拆分成单独的日期，并转换格式
dates_list = dates_string.strip().split('\n')
formatted_dates = [f'{int(date.split("-")[0]):02d}/{int(date.split("-")[1]):02d}/{date.split("-")[2]}' for date in dates_list]


# 检查两个文本是否完全匹配
are_texts_matching_dob = set(text_a_dob) == set(formatted_dates)
are_texts_matching_dob


# 如果不匹配
# 找出文本A和文本B中Name不同的内容
name_difference_a_b = set(text_a).difference(set(text_b_adjusted))
name_difference_b_a = set(text_b_adjusted).difference(set(text_a))

# 将找到的不同内容格式化为输出
different_content = {
    "在文本A中但不在文本B中的内容": list(difference_a_b),
    "在文本B中但不在文本A中的内容": list(difference_b_a)
}
different_content

# 如果不匹配
# 找出文本A和文本B中DOB不同的内容
dob_difference_a_b = set(text_a_dob).difference(set(formatted_dates))
dob_difference_b_a = set(formatted_dates).difference(set(text_a_dob))

# 将找到的不同内容格式化为输出
different_content = {
    "在文本A中但不在文本B中的内容": list(difference_a_b),
    "在文本B中但不在文本A中的内容": list(difference_b_a)
}
different_content
