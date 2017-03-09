require 'bundler/gem_tasks'
require 'rake/testtask'
require 'rspec/core/rake_task'
require 'rubocop/rake_task'

Dir['lib/fhir_client/tasks/**/*.rake'].sort.each do |ext|
  load ext
end

Rake::TestTask.new(:test) do |t|
  t.libs << 'test'
  t.libs << 'lib'
  t.test_files = FileList['test/**/*_test.rb']
  t.verbose = true
  t.warning = false
end

RSpec::Core::RakeTask.new

desc 'Run rubocop'
task :rubocop do
  RuboCop::RakeTask.new
end

task default: [:rubocop, :spec, :test]
