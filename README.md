# Add Document Tags

## Short description
The «Add Document Tags» extension is for OpenCart 3 CMS. It is a helper tool that extends standard OpenCart class "Document" by adding two methods - addTag and getTags to allow store and embed any html tags with custom attributes and content.

1. To add a tag use `$this->document->addTag($id, $tag, $content, $attrs, $group)`, where:
* $id is an unique id to identify this entry.
* $tag is a type of tag (e.g., 'script', 'link', 'meta', etc).
* $content is a content between opening and closing tags
* $attrs is an array of tag attributes with values (e.g., [href => '/', 'rel' => 'alternate'])
* $group is a group where the tag will be placed (e.g, 'header' or 'footer')

2.To get tags use something like the next:
```
$tags = ''.

if ($this->document->getTags('header')) {
    foreach ($this->document->getTags('header') as $tag) {
		if ($tag['id'] == $route) {
			$tags .= '<' . $tag['tag'];

			$attrs = '';

			foreach ($tag['attrs'] as $attr => $value) {
				$attrs .= $attr . '="' . $value . '" ';
			}

			$tags .= ' ' . $attrs;
			$tags .= '>';
			$tags .= $tag['content'];
			$tags .= '</' . $tag['tag'] . '>';
			$tags .= '</' . $tag['tag'] . '>';
		}
	}
}
```

## License
Licensed under the [MIT License](https://git.io/JqJe0)

