---
layout: post
category: android_code
---

Android Dialog 全屏的正确姿势：

这里使用的是DialogFragment，如果使用普通Dialog，方法类似。

```kotlin
  override fun onCreateView(inflater: LayoutInflater, container: ViewGroup?, savedInstanceState: Bundle?): View? {
    dialog?.window?.requestFeature(Window.FEATURE_NO_TITLE)
    return inflater.inflate(R.layout.dialog_full_screen, container, false)
  }
  override fun onActivityCreated(savedInstanceState: Bundle?) {
    super.onActivityCreated(savedInstanceState)
    dialog?.window?.let {
      it.setBackgroundDrawable(ColorDrawable(Color.parseColor("#00000000")))
      val dm = Resources.getSystem().displayMetrics
      it.setLayout(dm.widthPixels, dm.heightPixels)
      it.addFlags(WindowManager.LayoutParams.FLAG_TRANSLUCENT_STATUS)
    }
  }
```