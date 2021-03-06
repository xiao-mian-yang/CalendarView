# CalendarView
Android 平台上继承 View 实现的自定义日历控件.

# 效果图
 ![image](https://github.com/Airsaid/CalendarView/blob/master/gif/preview.gif)

# 使用步骤
1、布局中：
```
<com.arisaid.calendarview.widget.WeekView
    android:layout_width="match_parent"
    android:layout_height="30dp"
    android:layout_marginTop="10dp"
    android:background="@android:color/white"
    app:wv_textColor="#333333"
    app:wv_textSize="14sp"/>
    
<com.arisaid.calendarview.widget.CalendarView
    android:id="@+id/calendarView"
    android:layout_width="match_parent"
    android:layout_height="300dp"
    android:background="@android:color/white"
    app:cv_dayBackground="@drawable/bg_day_un_selected"
    app:cv_selectDayBackground="@drawable/bg_day_selected"
    app:cv_selectTextColor="@android:color/white"
    app:cv_textColor="#333333"
    app:cv_textSize="14sp"/>
```

2、设置已选天数数据（可选操作）：
```
mCalendarView.setSelectDate(initData());

private List<String> initData() {
    List<String> dates = new ArrayList<>();
    Calendar calendar = Calendar.getInstance(Locale.CHINA);
    SimpleDateFormat sdf = new SimpleDateFormat(mCalendarView.getDateFormatPattern(), Locale.CHINA);
    sdf.format(calendar.getTime());
    dates.add(sdf.format(calendar.getTime()));
    return dates;
}
```

3、设置监听器：
```
mCalendarView.setOnDateChangeListener(new CalendarView.OnDateChangeListener() {
    @Override
    public void onSelectedDayChange(@NonNull CalendarView view, boolean select, int year, int month, int day) {
        if(select){
            Toast.makeText(getApplicationContext()
                    , "选中了：" + year + "年" + (month + 1) + "月" + day + "日", Toast.LENGTH_SHORT).show();
        }else{
            Toast.makeText(getApplicationContext()
                    , "取消选中了：" + year + "年" + (month + 1) + "月" + day + "日", Toast.LENGTH_SHORT).show();
        }
    }
});
```

# 属性 & 方法
| 属性名| 方法| 作用 |
|------------|-----------|--------|
| cv_textColor| setTextColor(@ColorInt int textColor)|设置默认文字颜色 |
| cv_selectTextColor| setSelectTextColor(@ColorInt int textColor)|设置选中后文字颜色 |
| cv_textSize| setTextSize(float textSize)|设置默认文字大小 |
| cv_selectTextSize | setSelectTextSize(float textSize)|设置选中后文字大小 |
| cv_dayBackground | setDayBackground(Drawable background)|设置默认天的背景 |
| cv_selectDayBackground | setSelectDayBackground(Drawable background)|设置选中后天的背景 |
| cv_dateFormatPattern | setDateFormatPattern(String pattern)|设置日期格式化格式 |

## 联系我
- **QQ 群：** 5707887
- **Email：** airsaid1024@gmail.com
- **Blog：**[http://blog.csdn.net/airsaid](http://blog.csdn.net/airsaid)