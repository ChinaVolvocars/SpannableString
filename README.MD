### SpannableString的使用

> 效果图

![](https://github.com/ChinaVolvocars/SpannableString/blob/master/img/20170801115739.png)


- ForegroundColorSpan
- BackgroundColorSpan
- RelativeSizeSpan
- StrikethroughSpan
- UnderlineSpan
- SuperscriptSpan
- SubscriptSpan
- StyleSpan
- ImageSpan
- ClickableSpan
- URLSpan
- SpannableStringBuilder

Spanned.SPAN_INCLUSIVE_EXCLUSIVE  从起始下标到终了下标，包括起始下标
Spanned.SPAN_INCLUSIVE_INCLUSIVE  从起始下标到终了下标，同时包括起始下标和终了下标
Spanned.SPAN_EXCLUSIVE_EXCLUSIVE  从起始下标到终了下标，但都不包括起始下标和终了下标
Spanned.SPAN_EXCLUSIVE_INCLUSIVE  从起始下标到终了下标，包括终了下标

#### 1. ForegroundColorSpan，为文本设置前景色，效果和TextView的setTextColor()类似，实现方法如下：
```java
	 TextView textViewForegroundColorSpan = (TextView) findViewById(R.id.ForegroundColorSpan);
	 SpannableString spannableString = new SpannableString("设置文字的前景色为淡蓝色");
	 ForegroundColorSpan colorSpan = new ForegroundColorSpan(Color.parseColor("#0099EE"));
	 spannableString.setSpan(colorSpan, 9, spannableString.length(), Spanned.SPAN_INCLUSIVE_EXCLUSIVE);
	 textViewForegroundColorSpan.setText(spannableString);
```
#### 2. BackgroundColorSpan，为文本设置背景色，效果和TextView的setBackground()类，实现方法如下：
```java
        TextView textViewBackgroundColorSpan = (TextView) findViewById(R.id.BackgroundColorSpan);
        SpannableString spannableString1 = new SpannableString("设置文字的背景色为淡绿色");
        BackgroundColorSpan colorSpan1 = new BackgroundColorSpan(Color.parseColor("#AC00FF30"));
        spannableString1.setSpan(colorSpan1, 9, spannableString1.length(), Spanned.SPAN_INCLUSIVE_EXCLUSIVE);
        textViewBackgroundColorSpan.setText(spannableString1);
```
#### 3. RelativeSizeSpan，设置文字相对大小，在TextView原有的文字大小的基础上，相对设置文字大小，实现方法如下：
```java
        TextView textViewRelativeSizeSpan = (TextView) findViewById(R.id.RelativeSizeSpan);
        SpannableString relativeSizeSpanString = new SpannableString("万丈高楼平地起");

        RelativeSizeSpan sizeSpan01 = new RelativeSizeSpan(1.1f);
        RelativeSizeSpan sizeSpan02 = new RelativeSizeSpan(1.2f);
        RelativeSizeSpan sizeSpan03 = new RelativeSizeSpan(1.3f);
        RelativeSizeSpan sizeSpan04 = new RelativeSizeSpan(1.4f);
        RelativeSizeSpan sizeSpan05 = new RelativeSizeSpan(1.5f);
        RelativeSizeSpan sizeSpan06 = new RelativeSizeSpan(1.6f);
        RelativeSizeSpan sizeSpan07 = new RelativeSizeSpan(1.7f);

        relativeSizeSpanString.setSpan(sizeSpan01, 0, 1, Spanned.SPAN_INCLUSIVE_EXCLUSIVE);
        relativeSizeSpanString.setSpan(sizeSpan02, 1, 2, Spanned.SPAN_INCLUSIVE_EXCLUSIVE);
        relativeSizeSpanString.setSpan(sizeSpan03, 2, 3, Spanned.SPAN_INCLUSIVE_EXCLUSIVE);
        relativeSizeSpanString.setSpan(sizeSpan04, 3, 4, Spanned.SPAN_INCLUSIVE_EXCLUSIVE);
        relativeSizeSpanString.setSpan(sizeSpan05, 4, 5, Spanned.SPAN_INCLUSIVE_EXCLUSIVE);
        relativeSizeSpanString.setSpan(sizeSpan06, 5, 6, Spanned.SPAN_INCLUSIVE_EXCLUSIVE);
        relativeSizeSpanString.setSpan(sizeSpan07, 6, 7, Spanned.SPAN_INCLUSIVE_EXCLUSIVE);

        textViewRelativeSizeSpan.setText(relativeSizeSpanString);

```
#### 4. StrikethroughSpan，为文本设置中划线，也就是常说的删除线，实现方法如下：
```java
        TextView textViewStrikethroughSpan = (TextView) findViewById(R.id.StrikethroughSpan);
        SpannableString strikethroughSpanString = new SpannableString("为文字设置删除线");
        StrikethroughSpan strikethroughSpan = new StrikethroughSpan();
        strikethroughSpanString.setSpan(strikethroughSpan, 5, strikethroughSpanString.length(), Spanned.SPAN_INCLUSIVE_EXCLUSIVE);
        textViewStrikethroughSpan.setText(strikethroughSpanString);

```
####  5. UnderlineSpan，为文本设置下划线，具体实现方法如下：
```java
        TextView textViewUnderlineSpan = (TextView) findViewById(R.id.UnderlineSpan);
        SpannableString spannableStringUnderlineSpan = new SpannableString("为文本设置下划线");
        UnderlineSpan underlineSpan = new UnderlineSpan();
        spannableStringUnderlineSpan.setSpan(underlineSpan, 5, spannableStringUnderlineSpan.length(), Spanned.SPAN_INCLUSIVE_EXCLUSIVE);
        textViewUnderlineSpan.setText(spannableStringUnderlineSpan);
```
####  6. SuperscriptSpan，设置上标，具体实现方法如下：
```java
        TextView textViewSuperscriptSpan = (TextView) findViewById(R.id.SuperscriptSpan);
        SpannableString spannableStringSuperscriptSpan = new SpannableString("为文字设置上标");
        SuperscriptSpan superscriptSpan = new SuperscriptSpan();
        spannableStringSuperscriptSpan.setSpan(superscriptSpan, 5, spannableStringSuperscriptSpan.length(), Spanned.SPAN_INCLUSIVE_EXCLUSIVE);
        textViewSuperscriptSpan.setText(spannableStringSuperscriptSpan);
```
####  7. SubscriptSpan，设置下标，功能与设置上标类似，不做过多描述，具体实现方法如下：
```java
        TextView textViewSubscriptSpan = (TextView) findViewById(R.id.SubscriptSpan);
        SpannableString spannableStringSubscriptSpan = new SpannableString("为文字设置下标");
        SubscriptSpan subscriptSpan = new SubscriptSpan();
        spannableStringSubscriptSpan.setSpan(subscriptSpan, 5, spannableStringSuperscriptSpan.length(), Spanned.SPAN_INCLUSIVE_EXCLUSIVE);
        textViewSubscriptSpan.setText(spannableStringSubscriptSpan);
```

####  8. StyleSpan，为文字设置风格（粗体、斜体），和TextView属性textStyle类似，实现方法如下：
```java
        TextView textViewStyleSpan = (TextView) findViewById(R.id.StyleSpan);
        SpannableString spannableStringStyleSpan = new SpannableString("为文字设置粗体，斜体样式");
        StyleSpan styleSpanA = new StyleSpan(Typeface.BOLD);
        StyleSpan styleSpanB = new StyleSpan(Typeface.ITALIC);
        spannableStringStyleSpan.setSpan(styleSpanA, 5, 7, Spanned.SPAN_INCLUSIVE_EXCLUSIVE);
        spannableStringStyleSpan.setSpan(styleSpanB, 8, 10, Spanned.SPAN_INCLUSIVE_EXCLUSIVE);
        textViewStyleSpan.setHighlightColor(Color.parseColor("#36969696"));
        textViewStyleSpan.setText(spannableStringStyleSpan);
```

####  9. ImageSpan，设置文本图片，实现方法如下：
```java
        TextView textViewImageSpan = (TextView) findViewById(R.id.ImageSpan);
        SpannableString spannableStringImageSpan = new SpannableString("在文字中添加表情（表情）");
        Drawable drawable = getResources().getDrawable(R.drawable.im);
        drawable.setBounds(0, 0, 42, 42);
        ImageSpan imageSpan = new ImageSpan(drawable);
        spannableStringImageSpan.setSpan(imageSpan, 6, 8, Spanned.SPAN_INCLUSIVE_EXCLUSIVE);
        textViewImageSpan.setText(spannableStringImageSpan);
```

####  10.  ClickableSpan，设置可点击的文本，设置这个属性的文本可以相应用户点击事件，至于点击事件用户可以自定义， 就像效果图显示一样，用户可以实现点击跳转页面的效果，具体实现方法如下：
```java
        /*
         * 注意：使用ClickableSpan的文本如果想真正实现点击作用，必须为TextView设置setMovementMethod方法，
         * 否则没有点击相应，至于setHighlightColor方法则是控制点击是的背景色。
         */
        TextView textViewClickableSpan = (TextView) findViewById(R.id.ClickableSpan);
        SpannableString spannableStringClickableSpan = new SpannableString("为文字设置点击事件");
        MyClickableSpan myClickableSpan = new MyClickableSpan("我一个人就是一支军队");
        spannableStringClickableSpan.setSpan(myClickableSpan, 5, spannableStringClickableSpan.length(), Spanned.SPAN_INCLUSIVE_EXCLUSIVE);
        textViewClickableSpan.setMovementMethod(LinkMovementMethod.getInstance());
        textViewClickableSpan.setHighlightColor(Color.parseColor("#36969696"));

        textViewClickableSpan.setText(spannableStringClickableSpan);
		
		
    class MyClickableSpan extends ClickableSpan {

        private String content;

        public MyClickableSpan(String s) {
            this.content = s;
        }

        @Override
        public void updateDrawState(TextPaint ds) {
            ds.setUnderlineText(false);//设置被点击的文字没有下划线
        }

        @Override
        public void onClick(View widget) {
            Toast.makeText(MainActivity.this, content, Toast.LENGTH_SHORT).show();
        }
    }
```
####  11. URLSpan，设置超链接文本
```java
        /**
         * URLSpan，设置超链接文本，其实聪明的小伙帮在讲到ClickableSpan的时候就能实现超链接文本的效果了，
         * 重写onClick点击事件就行，也确实看了URLSpan的源码，URLSpan就是继承自ClickableSpan，也和想象中一样，
         * 就是重写了父类的onClick事件，用系统自带浏览器打开链接，具体实现方法如下：
         */
        TextView textViewURLSpan = (TextView) findViewById(R.id.URLSpan);
        SpannableString spannableStringURLSpan = new SpannableString("为文字设置超链接");
        URLSpan urlSpan = new URLSpan("https://github.com/ChinaVolvocars");
        spannableStringURLSpan.setSpan(urlSpan, 5, spannableStringURLSpan.length(), Spanned.SPAN_INCLUSIVE_EXCLUSIVE);
        textViewURLSpan.setMovementMethod(LinkMovementMethod.getInstance());
        textViewURLSpan.setHighlightColor(Color.YELLOW);
        textViewURLSpan.setText(spannableStringURLSpan);
```

#### SpannableStringBuilder
```java
应该有不少开发的小伙伴知道StringBuilder，可以使用append()方法实现字符串拼接，非常方便。同样，SpannableString中也有SpannableStringBuilder，顾名思义，就是实现对，SpannableString的一个拼接效果，同样是append()方法，可以实现各种风格效果的SpannableString拼接，非常实用。
```