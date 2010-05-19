require 'toto'

@config = Toto::Config::Defaults

task :default => :new

desc "Create a new article."
task :new do
  title = ask('Title: ')
  slug = title.empty?? nil : title.strip.slugize

  article = {'title' => title, 'date' => Time.now.strftime("%d/%m/%Y")}.to_yaml
  article << "\n"
  article << "Once upon a time...\n\n"

  path = "#{Toto::Paths[:articles]}/#{Time.now.strftime("%Y-%m-%d")}#{'-' + slug if slug}.#{@config[:ext]}"

  unless File.exist? path
    File.open(path, "w") do |file|
      file.write article
    end
    toto "an article was created for you at #{path}."
  else
    toto "I can't create the article, #{path} already exists."
  end
end

desc "Publish my blog."
task :publish do
<<<<<<< HEAD
  toto "Publishing your article(s)..."

  `git add -A`
  `git commit -a -m "$(date)"`
=======
  toto "publishing your article(s)..."
>>>>>>> 6b9b23fff87de67ea58991dd495972fc9f02b75d
  `git push heroku master`
end

def toto msg
  puts "\n  toto ~ #{msg}\n\n"
end

def ask message
  print message
  STDIN.gets.chomp
end

