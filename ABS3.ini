import pandas as pd

def count_jobs_with_skill(filename, skill):
    """
    این تابع فایل CSV را می‌خواند و تعداد مشاغلی که مهارت موردنظر در ستون 'مهارت‌ها' دارند را محاسبه می‌کند.
    """
    # خواندن فایل CSV به دیتا فریم pandas
    df = pd.read_csv(filename)

    # اطمینان از اینکه ستون مهارت‌ها متنی است و بررسی وجود مهارت
    df['مهارت‌ها'] = df['مهارت‌ها'].astype(str)

    # فیلتر کردن ردیف‌هایی که مهارت خاص را در مهارت‌ها شامل می‌شوند (حساس به حروف کوچک و بزرگ نیست)
    filtered = df[df['مهارت‌ها'].str.contains(skill, case=False)]

    count = filtered.shape[0]

    return count, filtered

if __name__ == "__main__":
    filename = 'jobs.csv'
    skill_to_search = 'پایتون'

    # محاسبه تعداد مشاغل مرتبط با مهارت
    count, filtered_jobs = count_jobs_with_skill(filename, skill_to_search)

    # نمایش نتایج در کنسول
    print(f"تعداد مشاغل مرتبط با مهارت '{skill_to_search}': {count}")
    print("\nلیست مشاغل مربوطه:")
    print(filtered_jobs.to_string(index=False))

    # ذخیره نتایج در فایل متنی
    with open('output.txt', 'w', encoding='utf-8') as f:
        f.write(f"تعداد مشاغل مرتبط با مهارت '{skill_to_search}': {count}\n\n")
        f.write(filtered_jobs.to_string(index=False))