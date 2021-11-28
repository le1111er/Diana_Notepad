# Diana_Notepad

## 1.主界面
   ### 更新了图标与应用名称，同时对note标签进行了一定程度的美化
![image](https://github.com/le1111er/Diana_Notepad/blob/c66da49123cfb599123c3aa98c79b91d256c521f/app/src/main/res/drawable/mainpage.png)
 ```xml
    <?xml version="1.0" encoding="utf-8"?>
    <shape xmlns:android="http://schemas.android.com/apk/res/android">
    <solid android:color="#99CCFF" />
    <corners android:topLeftRadius="20dp"
        android:topRightRadius="20dp"
        android:bottomRightRadius="20dp"
        android:bottomLeftRadius="20dp"/>
    <stroke android:width="1dp" android:color="#000000" />
    </shape>
 ```
   ### 更改背景功能
![image](https://github.com/le1111er/Diana_Notepad/blob/bb89d5378eeb93a7dd8e19e96e2edb7a0f0cfaa2/app/src/main/res/drawable/mainmenu.png)
![image](https://github.com/le1111er/Diana_Notepad/blob/a89227a61fb184730e56e3a63304e1fe93f44789/app/src/main/res/drawable/skin1.png)
![image](https://github.com/le1111er/Diana_Notepad/blob/a89227a61fb184730e56e3a63304e1fe93f44789/app/src/main/res/drawable/skin2.png)
```java
    /*
       背景颜色选择框
    */
    private  void showpopSelectBgWindows() {
        LayoutInflater inflater = LayoutInflater.from(this);
        View view = inflater.inflate(R.layout.dialog_bg_select_layout, null);
        AlertDialog.Builder builder = new AlertDialog.Builder(this);
        builder.setTitle("背景");//设置标题
        builder.setView(view);
        AlertDialog dialog = builder.create();//获取dialog
        dialog.show();//显示对话框
    }

    /*
    背景改变的监听
     */
    public void ColorSelect(View view) {
        String color;
        switch(view.getId()) {
            case R.id.Diana1:
                /*此处进行背景颜色修改,后改为主题效果*/
                Drawable btnDrawable1 = getResources().getDrawable(R.drawable.dianaa);
                ll_noteList.setBackgroundDrawable(btnDrawable1);
                lv_notesList.setBackgroundDrawable(btnDrawable1);

                break;
            case R.id.Diana2:
                Drawable btnDrawable2 = getResources().getDrawable(R.drawable.dianab);
                ll_noteList.setBackgroundDrawable(btnDrawable2);
                lv_notesList.setBackgroundDrawable(btnDrawable2);
                break;
            case R.id.Diana3:
                Drawable btnDrawable3 = getResources().getDrawable(R.drawable.dianac);
                ll_noteList.setBackgroundDrawable(btnDrawable3);
                lv_notesList.setBackgroundDrawable(btnDrawable3);
                break;
            case R.id.Diana4:
                Drawable btnDrawable4 = getResources().getDrawable(R.drawable.dianad);
                ll_noteList.setBackgroundDrawable(btnDrawable4);
                lv_notesList.setBackgroundDrawable(btnDrawable4);
                break;
            case R.id.Diana5:
                Drawable btnDrawable5 = getResources().getDrawable(R.drawable.dianae);
                ll_noteList.setBackgroundDrawable(btnDrawable5);
                lv_notesList.setBackgroundDrawable(btnDrawable5);
                break;
            case R.id.Diana6:
                Drawable btnDrawable6 = getResources().getDrawable(R.drawable.dianaf);
                ll_noteList.setBackgroundDrawable(btnDrawable6);
                lv_notesList.setBackgroundDrawable(btnDrawable6);
                break;
            case R.id.Diana7:
                Drawable btnDrawable7 = getResources().getDrawable(R.drawable.dianag);
                ll_noteList.setBackgroundDrawable(btnDrawable7);
                lv_notesList.setBackgroundDrawable(btnDrawable7);
                break;
        }
```
```java

```
   ### 时间戳功能
```java
public class NoteBean {
    private String Title; //笔记的标题
    private String createTime; //笔记的创建时间
    private String Cursor_id; //所属的游标的position

    public NoteBean(String title, String createTime) {
        Title = title;
        this.createTime = createTime;
    }

    public NoteBean(String title, String createTime, String cursor_id) {
        Title = title;
        this.createTime = createTime;
        Cursor_id = cursor_id;
    }

    public NoteBean(String title, String createTime, String cursor_id, Cursor cursor) {
        Title = title;
        this.createTime = createTime;
        Cursor_id = cursor_id;
    }

    public String getTitle() {
        return Title;
    }

    public void setTitle(String title) {
        Title = title;
    }

    public String getCreateTime() {
        return createTime;
    }

    public void setCreateTime(String createTime) {
        this.createTime = createTime;
    }

    public String getCursor_id() {
        return Cursor_id;
    }

    public void setCursor_id(String cursor_id) {
        Cursor_id = cursor_id;
    }


}
```
```java
public class DateUtil {
    public static String StringToDate(String str_data) {
        String beginDate = str_data;
        SimpleDateFormat sdf = new SimpleDateFormat("yyyy-MM-dd HH:mm:ss");
        String sd = sdf.format(new Date(Long.parseLong(beginDate)));
        return  sd;
    }
}
```
  ### 搜索功能
  ![image](https://github.com/le1111er/Diana_Notepad/blob/a89227a61fb184730e56e3a63304e1fe93f44789/app/src/main/res/drawable/find.png)
## 2.编辑界面
![image](https://github.com/le1111er/Diana_Notepad/blob/bb89d5378eeb93a7dd8e19e96e2edb7a0f0cfaa2/app/src/main/res/drawable/editor.png)
<br>Debug Note:上锁功能待添加，仅实现弹窗</br>
