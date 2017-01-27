# Replace the placeholders with your own details for this code to work. Otherwise you will get an error. 
# Put your own details for the username, email and the bitbucket git address for the repository that you created.

require 'tmpdir'

desc "Generate jekyll site"
task :generate do
  puts "## Generating Site with Jekyll"
  system "jekyll build"
end

desc "Generate and publish blog to Bitbucket"
task :publish do
  Dir.mktmpdir do |tmp|
    system "mv _site/* #{tmp}"
    system "git checkout -b aerobatic"
    system "rm -rf *"
    system "mv #{tmp}/* ."    
    system 'git config --global user.email "dhillonv10@knights.ucf.edu"'
    system 'git config --global user.name "opsbug"'
    system "git add ."
    system "git commit -am 'Codeship Update'"
    system "git remote add bb git@bitbucket.org:opsbug/design-studio.git"
    system "git push -f bb aerobatic"
  end
end