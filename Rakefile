require "rake/testtask"
require "bundler/gem_tasks"
require "find"

desc 'Say hello'
task :hello do
  puts "Hello there. This is the 'hello' task"
end

desc "List all files that aren't hidden, or contained in hidden folders"
task :list_files do
  Find.find('.') do |path|
    next if path.start_with?('./.')
    puts path if File.file?(path)
  end
end

desc 'Display inventory of all files'
task :inventory do
  Find.find('.') do |name|
    next if name.include?('/.') # Excludes files and directories with . names
    puts name if File.file?(name)
  end
end

desc 'my test (default)'
task :default => :test

Rake::TestTask.new(:test) do |t|
  t.libs << "test"
  t.libs << "lib"
  t.test_files = FileList['test/**/*_test.rb']
end