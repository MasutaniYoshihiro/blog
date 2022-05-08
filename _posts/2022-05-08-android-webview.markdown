---
layout: post
title:  AndroidのWebViewで戻るを実装したい
date:   2022-05-08 22:33:25 +0900
categories: Android
tag: article
---

## 概要
WebViewで特定のサイトを表示することはできるけど、<br>
戻るとか、<br>
進むとか、<br>
閉じるとか、そういったユーザーアクションをきちんと実装するにはデフォルトの挙動だけだとうまく行かない。

例えば、デフォルトの戻るの挙動のままだと本当は前のページに戻って欲しいのに、<br>
Activityが閉じられたりして困ってしまう。<br>
そんなときは、デフォルトの挙動を書き換える必要がある。

1. getOnBackProssedDispatcherにコールバックを追加する

## 手順
### 1.getOnBackProssedDispatcherにコールバックを追加する
onCreateでデフォルトの「戻る」アクションのイベントハンドラにコールバックを追加することで独自のイベントを処理できる。
WebViewのgoBack()でHistoryBackが実装できる。

```java
public class MyWebViewFragment extends Fragment {
    // WebView
    private WebView mWebView;

    @Override
    public void onCreate(@Nullable Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);

        // callbackの定義
        OnBackPressedCallback callback = new OnBackPressedCallback(true) {
            @Override
            public void handleOnBackPressed() {
                if (mWebView.canGoBack()) {
                    // Webページ内のHistoryBack
                    mWebView.goBack();
                }
            }
        };
        // callbackの登録
        requireActivity().getOnBackPressedDispatcher().addCallback(this, callback);
    }

    @Override
    public View onCreateView(LayoutInflater inflater, ViewGroup container,Bundle savedInstanceState) {
        View view = inflater.inflate(R.layout.shop_fragment, container, false);
        // webviewをインスタンスとして保持
        mWebView= (WebView) view.findViewById(R.id.webview);
        mWebView.setWebViewClient(new WebViewClient());
        mWebView.loadUrl("http://example.com");
        return view
    }
}
```

## 参考
[適切な「戻る」ナビゲーションを提供する](https://developer.android.com/guide/navigation/navigation-custom-back?hl=ja)
