{{- $datetime := time .Date -}}
{{- $day := $datetime.Day -}}
{{- $suffix := "th" -}}
{{- if (and (ne (mod $day 100) 11) (ne (mod $day 100) 12) (ne (mod $day 100) 13)) -}}
{{- if eq (mod $day 10) 1 -}} {{- $suffix = "st" -}}
{{- else if eq (mod $day 10) 2 -}} {{- $suffix = "nd" -}}
{{- else if eq (mod $day 10) 3 -}} {{- $suffix = "rd" -}}
{{- end -}}
{{- end -}}

---

title: "{{ $datetime.Format "Jan" }} {{ $day }}{{ $suffix }}, {{ $datetime.Format "2006" }}"
date: {{ .Date }}
draft: false
categories: ["journal"]

---
