rule '.html' => '.md' do |t|
  sh "echo hello > #{t.name}"
end


task :default => Dir.glob('**/*.md').map { |filename| filename.ext '.html' }
