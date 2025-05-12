+++
title = '{{ replace .File.ContentBaseName "-" " " | title }}'
date = '{{ time.Now.Year }}-{{ time.Now.Month | int | fmt.Printf "%02d" }}-{{ time.Now.Day | fmt.Printf "%02d" }}'
draft = true
[params]
  author = '{{ .Site.Params.chairman }}'
  chairman = '{{ .Site.Params.chairman }}'
  {{- with .Site.Params.repdirectors }}
  repdirectors = {{ apply . "fmt.Printf" "'%s'" "." }}
  {{- end }}
  {{- with .Site.Params.directors }}
  directors = {{ apply . "fmt.Printf" "'%s'" "." }}
  {{- end }}
  location = '{{ .Site.Params.location }}'
  [start]
    hour = {{ .Site.Params.start.hour }}
    minute = {{ .Site.Params.start.minute }}
  [end]
    hour = {{ .Site.Params.end.hour }}
    minute = {{ .Site.Params.end.minute }}
+++
