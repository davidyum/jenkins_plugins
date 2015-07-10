require 'rspec/core/rake_task'
require 'rubocop/rake_task'
require 'foodcritic'

RuboCop::RakeTask.new(:rubocop)

FoodCritic::Rake::LintTask.new(:foodcritic)

begin
  require 'kitchen/rake_tasks'
  Kitchen::RakeTasks.new
rescue LoadError
  puts '>>>>> Kitchen gem not loaded, omitting tasks' unless ENV['CI']
end

task default: [:rubocop, :foodcritic]
