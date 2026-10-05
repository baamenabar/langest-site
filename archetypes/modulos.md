{{- if strings.HasSuffix .Name "_index.md" -}}
---
title: '{{ replace (strings.TrimSuffix "_index.md" .Name) "-" " " | title }}'
description: ""
date: '{{ .Date }}'
draft: true
modulo: '{{ path.Base .File.Dir }}'
status: borrador
categories: [aventura]
tags: []
locations: []
factions: []
---
{{- else -}}
---
title: '{{ replace (strings.TrimSuffix ".md" .Name) "-" " " | title }}'
description: ""
date: '{{ .Date }}'
draft: true
modulo: '{{ path.Base .File.Dir }}'
categories: [aventura]
tags: []
locations: []
factions: []
---
{{- end -}}