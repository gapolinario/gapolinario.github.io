---
layout: post
title:  "Vim mappings and shortcuts"
date:   2019-09-30 18:00:00 -0300
categories: linux, vim
---

I created these vim shortcuts, which replace False with True and True with False
and can be easily called with the `,mt` command (make true) and `,mf` command (make false)

	nnoremap ,mt :s/False/True/<CR>
	nnoremap ,mf :s/True/False/<CR>

[This][map] is a great tutorial on the details of the vim mappings and shortcuts
and [this][rep] is a reference on search and replace

[maps]: https://medium.com/vim-drops/understand-vim-mappings-and-create-your-own-shortcuts-f52ee4a6b8ed
[rep]: https://www.linux.com/tutorials/vim-tips-basics-search-and-replace/