[![Download](https://api.bintray.com/packages/jiangyychn/maven/dialog/images/download.svg)](https://bintray.com/jiangyychn/maven/dialog)
![API](https://img.shields.io/badge/api-14%2B-brightgreen.svg)

## Download

```
dependencies {
    compile 'com.jiangyy:dialog:1.0.2'
}
```

## How do I use Dialog

### CommonDialog

![CommonDialog](http://img.blog.csdn.net/20170808213610557?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvanlqODQ5MTE1Mjg3/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

```
new CommonDialog.Builder(this)
                .setTitle("标题")
                .setMessage("这里是提示内容")
                .setPositiveButton("确定", new View.OnClickListener() {
                    @Override
                    public void onClick(View view) {

                    }
                }).setNegativeButton("取消", null).show();
```


### SingleChoiceDialog

![SingleChoiceDialog](http://img.blog.csdn.net/20170808213904553?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvanlqODQ5MTE1Mjg3/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

```
new SingleChoiceDialog.Builder(this)
				.setTitle("提示")
                .addList(new String[]{"1", "2", "3"})
                .setOnItemClickListener(new SingleChoiceDialog.OnItemClickListener() {
                    @Override
                    public void OnItemClick(String title, int position) {
                        Toast.makeText(MainActivity.this, title + "," + position, Toast.LENGTH_SHORT).show();
                    }
                })
                .show();
```

### MultipleChoiceDialog

![MultipleChoiceDialog](http://img.blog.csdn.net/20170808214043223?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvanlqODQ5MTE1Mjg3/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

```
new MultipleChoiceDialog.Builder(this)
				.setTitle("提示")
                .addList(new String[]{"1", "2", "3"})
                .addListener(new MultipleChoiceDialog.ClickListener() {
                    @Override
                    public void OnFinishClick(List<String> data, List<Integer> data0) {
                        String str = "";
                        for (int index = 0; index < data.size(); index++) {
                            str += "," + data.get(index);
                        }
                        Toast.makeText(MainActivity.this, str, Toast.LENGTH_SHORT).show();
                    }
                }).show();
```

### InputDialog

![InputDialog](http://img.blog.csdn.net/20170808214448788?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvanlqODQ5MTE1Mjg3/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

```
new InputDialog.Builder(this)
                .setTitle("请输入")
                .setHint("这里是提示内容")
                .setLines(5)
                .setPositiveButton("确定", new View.OnClickListener() {
                    @Override
                    public void onClick(View view) {
                        Toast.makeText(MainActivity.this, view.getTag().toString(), Toast.LENGTH_SHORT).show();
                    }
                }).setNegativeButton("取消", null).show();
```

### LoadingDialog

![LoadingDialog](http://img.blog.csdn.net/20170808214759126?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvanlqODQ5MTE1Mjg3/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

```
	final LoadingDialog.Builder mBuilder = new LoadingDialog.Builder(this);
        mBuilder.setTitle("正在加载ing...");
        mBuilder.showProgress(true).show();

        new Thread(new Runnable() {

            @Override
            public void run() {
                int i = 0;
                while (i < 100) {
                    try {
                        Thread.sleep(200);
                        mBuilder.setProgress(i);
                        i++;
                    } catch (Exception e) {
                    }
                }
                mBuilder.dismiss();
            }
        }).start();
```

### UpdateDialog

![UpdateDialog](http://img.blog.csdn.net/20170808214851846?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvanlqODQ5MTE1Mjg3/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

```
new UpdateDialog.Builder(this)
                .setIcon(R.mipmap.ic_launcher)
                .setTitle("发现新版本，1.0.1来了")
                .setMessage("【新添】1、添加功能一；\n【修复】2、修复了好几个BUG哟\n【其他】3、你猜更新了什么", R.color.colorAccent)
                .setPositiveButton("立即下载", new View.OnClickListener() {
                    @Override
                    public void onClick(View view) {

                    }
                }).setNegativeButton("以后更新", null).show();
```
