# gamedev

;; Base org directory
(setq org-directory "~/org/")

;; Make gamedev files easy to jump to
(defvar gamedev-dir (concat org-directory "gamedev/"))

;; Capture templates: quick-add notes into the right file without
;; manually opening it first
(after! org
  (setq org-capture-templates
        (("g" "Gamedev note...")  ; parent menu, no template of its own

          ("ge" "DoomEmacs note" entry
           (file+headline ,(concat gamedev-dir "doomemacs.org") "Inbox")
           "* %?\n%U\n%a\n")

          ("gb" "Blender note" entry
           (file+headline ,(concat gamedev-dir "blender.org") "Inbox")
           "* %?\n%U\n%a\n")

          ("gc" "Collision note" entry
           (file+headline ,(concat gamedev-dir "collision.org") "Inbox")
           "* %?\n%U\n%a\n")

          ("gs" "Shader note" entry
           (file+headline ,(concat gamedev-dir "shaders.org") "Inbox")
           "* %?\n%U\n%a\n")

          ("gv" "Vulkan note" entry
           (file+headline ,(concat gamedev-dir "vulkan.org") "Inbox")
           "* %?\n%U\n%a\n")

          ("gd" "D3D11 note" entry
           (file+headline ,(concat gamedev-dir "d3d11.org") "Inbox")
           "* %?\n%U\n%a\n")

          ("gm" "Math note" entry
           (file+headline ,(concat gamedev-dir "math.org") "Inbox")
           "* %?\n%U\n%a\n")

          ("gg" "Gotcha" entry
           (file+headline ,(concat gamedev-dir "gotchas.org") "Inbox")
           "* %?\n%U\n%a\n"))))

;; RSS feeds
(setq elfeed-feeds
      '("https://www.youtube.com/feeds/videos.xml?channel_id=UCaTznQhurW5AaiYPbhEA-KA"
        "https://www.youtube.com/feeds/videos.xml?channel_id=UCLRILFZ-sHKYZ8io_IP5_ag"
        "https://www.youtube.com/feeds/videos.xml?channel_id=UC9J9u3apteD0EuFjzRpt71w"
        "https://www.youtube.com/feeds/videos.xml?channel_id=UCc6-nJ-sW4ZEH3bTOMDHsaQ"
        "https://www.youtube.com/feeds/videos.xml?channel_id=UC8biKfVSZgnwKQiK24ltiEw"
        "https://www.youtube.com/feeds/videos.xml?channel_id=UChXKAI83IuqSneWe92F97jQ"))

(map! :leader
      :desc "elfeed" "o y" #'elfeed)
;
