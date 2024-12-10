---
Title: Simple language switcher for HUGO
Date: 09 Dec 2024
Summary: Made as minimalistic as possible
---

![lang-switcher](/img/language-switcher/lang-switch.gif)

A straightforward language switcher with just a few lines of code. The result is a list of available languages that are specified in your Hugo config (hugo.toml).

Here is code for header.html

```go-template
<ul class="language-toggle">
    {{ range site.Home.AllTranslations }} 
    {{if eq .Language.Lang site.Language.Lang}}
    <li href="{{ .RelPermalink }}">
      {{ .Language.LanguageName }}
      <img class="language-icon" src="flaticon.io" alt="Arrow down" />
    </li>
    {{ end }} 
    {{end}} 
    {{range site.Home.AllTranslations}} 
    {{if ne .Language.Langsite.Language.Lang}}
    <li><a href="{{ .RelPermalink }}">{{ .Language.LanguageName }}</a></li>
    {{end}} 
    {{end}}
  </ul>
```

Let’s break it down to step by step:

`site.Home.AllTranslations` is are taking all translations of home page of website

`if eq .Language.Lang site.Language.Lang` if the current website language matches one of the available languages, it will appear at the top of the list. You should remove the `<a></a>` tags to prevent issues with the language switcher on mobile devices, as :hover can cause problems for touch users.

`.Language.LanguageName` shows language that is displayed. Name is indicated in config file.

`if ne .Language.Lang site.Language.Lang` if it’s not one of the languages that website is using right now, they are shown below.

I had challenges with `.Site` and `site`. The rule of thumb is if you meeting some kind of error with `.Site` - use `site`. `.Site` - is local, `site` is global variable.

Additionally, you would want for website logo to lead to the home page of chosen language. It also can be archived made with following code:

```go-template
{{ range site.Home.AllTranslations }} 
{{if eq .Language.Lang site.Language.Lang}}
<a href="{{ .RelPermalink }}">YOUR_LOGO</a>
{{ end }} 
{{end}}
```
