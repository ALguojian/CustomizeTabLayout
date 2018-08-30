# 自定义tablayout子view，控制下划线宽度

[![](https://jitpack.io/v/ALguojian/CustomizeTabLayout.svg)](https://jitpack.io/#ALguojian/CustomizeTabLayout)

1. Add the JitPack repository to your build file
```
allprojects {
    repositories {
            ...
            maven { url 'https://jitpack.io' }
        }
    }
```

Step 2. Add the dependency
```
dependencies {
                implementation 'com.github.ALguojian:CustomizeTabLayout:1.0.0'
        }
```

使用如下：

```
  <com.alguojian.demo.CustomizeTabLayout
        android:id="@+id/tablayout"
        android:layout_width="match_parent"
        android:layout_height="60dp"
        app:tabIndicatorHeight="2dp"
        app:tabIndicatorWidth="25dp"
        app:tabTextColor="#999999"
        app:tab_Mode="mode_fixed"
        android:layout_marginBottom="10dp"
        app:tabSelectTextColor="@color/colorPrimary"
        app:tabIndicatorColor="@color/colorAccent"
        app:tabTextSize="12sp"/>
```

```
        tabLayout = findViewById(R.id.tablayout);
        viewpager = findViewById(R.id.viewpager);

        ArrayList<String> strings = new ArrayList<>();
        strings.add("轻轻微微");
        strings.add("轻微轻微");

        ArrayList<Fragment> fragments = new ArrayList<>();
        fragments.add(BaseFragment.newInstance());
        fragments.add(BaseFragment.newInstance());

        tabLayout.addTabs(strings);
        viewpager.setAdapter(new BasePagerAdapter(getSupportFragmentManager(), fragments, strings));
        tabLayout.setupWithViewPager(viewpager);
        viewpager.addOnPageChangeListener(new TabLayout.TabLayoutOnPageChangeListener(tabLayout.getTabLayout()));

```