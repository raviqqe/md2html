require 'xml-dsl'
require 'rake/clean'
require 'redcarpet'



def markdown_to_html markdown
  Redcarpet::Markdown::new(Redcarpet::Render::HTML).render markdown
end


rule '.html' => '.md' do |t|
  html = xml do
    html do
      head do
        title "raviqqe's notes"
        link rel: 'stylesheet', href: '/style.css'
      end

      body markdown_to_html(File.read t.source)
    end
  end

  File.write t.name, html.to_s
end


task :default => Dir.glob('**/*.md').map { |filename| filename.ext '.html' }


CLEAN.include Dir.glob('**/*.html')
