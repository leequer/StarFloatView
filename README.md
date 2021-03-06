# StarFloatView

## 示例：
<img src="https://github.com/ErChenZhang/StarFloatView/blob/master/floatviewlib/src/main/res/drawable/readme_1.gif" width = "350" height = "600" alt="截图" align=center />

#### 支持自定义背景，自定义小球颜色、大小、以及默认小球文字

## 使用方法：
### 在工程目录的build.gradle中添加JitPack.io的代码仓库地址

    allprojects {
      repositories {
        ...
        maven { url 'https://jitpack.io' }
      }
    }
    
### 项目目录中的build.gradle中添加依赖

    ependencies {
        compile 'com.github.ErChenZhang:StarFloatView:v1.1'
	}

    

  ### 在布局文件中使用
    
         <com.smoke.zhangchen.floatviewlib.FloatView
            android:id="@+id/float_view"
            android:layout_width="match_parent"
            android:layout_height="wrap_content
            app:childTextColor="#ff0000"
            app:defaultViewText="正在生成中"
            app:chidTextSize="6sp"
            app:parentViewBackground="@mipmap/star_bg"
            app:childViewBackground="@drawable/shape_circle">
            
1. **childTextColor**:小球文字颜色大小，默认白色
2. **defaultViewText**:默认小球显示文字
3. **parentViewBackground**：整体背景
4. **childViewBackground**：小球背景
5. **chidTextSize**：小球文字大小，默认6sp
        
   ### 设置数据
   #### 当前数据支持int、long、float、double
    
         List<Float> list = new ArrayList<>();
            list.add((float) 1.245);
            list.add((float) 1.567);
            list.add((float) 0.261);
            floatview.setList(list);
            
  ### 小球点击回调（value.floatValue()对应传入的list类型）
     
        floatview.setOnItemClickListener(new FloatView.OnItemClickListener() {
            @Override
            public void itemClick(int position, Number value) {
                Toast.makeText(MainActivity.this, "当前是第"+position+"个，其值是"+value.floatValue(), Toast.LENGTH_SHORT).show();
            }
        });
            
