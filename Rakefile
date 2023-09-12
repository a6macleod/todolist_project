require 'rake/testtask'
require 'find'
require 'bundler/gem_tasks'

desc 'Say hello'
task :hello do
  puts "Hello there. This is the 'hello' task."
end

desc 'List all files'
task :list do
  Find.find('.') do |name|
    next if name.include?('/.') # excludes files and directories with . names
    puts name if File.file?(name)
  end
end

desc 'run tests'
task :default => :test

Rake::TestTask.new(:test) do |t|
  t.libs << "test"
  t.libs << "lib"
  t.test_files = FileList['test/**/*_test.rb']
end
