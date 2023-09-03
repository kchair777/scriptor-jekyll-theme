# Jekyll 4.0에는 몇 가지 주요 변경 사항이 포함되어 있습니다. 특히:

   * 이제 'link' 태그에 'relative_url' 필터가 통합되어 제공됩니다.
     더 이상 `{% link foo.md %}` 앞에 `{{ site.baseurl }}`을 추가하면 안 됩니다.
     자세한 내용은 https://github.com/jekyll/jekyll/pull/6727을 참조하세요.

   * 이제 'post_url' 태그에 'relative_url' 필터가 통합되어 제공됩니다.
     `{% post_url 2019-03-27-hello %}` 앞에 `{{ site.baseurl }}`을 추가하면 안 됩니다.
     자세한 내용은 https://github.com/jekyll/jekyll/pull/7589를 참조하세요.

   * 더 이상 사용되지 않는 구성 옵션에 대한 지원이 제거되었습니다. 우리는 더 이상
     경고를 출력하고 그 값을 새로운 대응 항목에 적절하게 할당합니다.
     내부적으로.