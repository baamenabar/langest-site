{{- $dir := .File.Dir -}}
{{- if strings.HasSuffix .Name "_index.md" -}}
---
title: '{{ replace (strings.TrimSuffix "_index.md" .Name) "-" " " | title }}'
description: ""
date: '{{ .Date }}'
draft: true
campaign: '{{ path.Base $dir }}'
status: activa
categories: []
tags: []
locations: []
factions: []
---
{{- else if strings.Contains $dir "/sessions/" -}}
---
title: '{{ replace (strings.TrimSuffix ".md" .Name) "-" " " | title }}'
description: ""
date: '{{ .Date }}'
draft: true
game_date: ""
campaign: '{{ path.Base (path.Dir $dir) }}'
adventure: ""
categories: [sesion]
tags: []
locations: []
factions: []
aliases: []
---
{{- else -}}
---
title: '{{ replace (strings.TrimSuffix ".md" .Name) "-" " " | title }}'
description: ""
date: '{{ .Date }}'
draft: true
campaign: '{{ path.Base (path.Dir $dir) }}'
categories: [referencia]
tags: []
---
{{- end -}}