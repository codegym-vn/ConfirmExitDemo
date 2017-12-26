# ConfirmExitDemo

#### Khởi tạo project với activity
```java
public class MainActivity extends AppCompatActivity {

   @Override
   protected void onCreate(Bundle savedInstanceState) {
       super.onCreate(savedInstanceState);
       setContentView(R.layout.activity_main);

   }
}
```

#### Tạo AlertDialog hiển thị nội dung thông báo như sau
```java
public class MainActivity extends AppCompatActivity {

   ...

   private void showAlertConfirmExit() {
       new AlertDialog.Builder(this)
               .setTitle("Thoát ứng dụng")
               .setMessage("Bạn muốn thoát ứng dụng?")
               .setPositiveButton("Đồng ý", new    DialogInterface.OnClickListener() {
        @Override
         public void onClick(DialogInterface dialogInterface, int i) {
                       MainActivity.this.finish();
                   }
         })
               .setNegativeButton("Hủy", new DialogInterface.OnClickListener() {
                   @Override
                   public void onClick(DialogInterface dialogInterface, int i) {
                       dialogInterface.dismiss();
                   }
               }).show();
   } 
}
```
#### Từ class Activity @override lại method OnBackPressed()
```java
public class MainActivity extends AppCompatActivity {

	   ......

   @Override
   public void onBackPressed() {
      super.onBackPressed();
   }
}
```
#### Sửa lại method onBackPressed() như sau
```java
@Override
public void onBackPressed() {
   //super.onBackPressed();
   showAlertConfirmExit();
}
```
Run project.Kết quả
	
