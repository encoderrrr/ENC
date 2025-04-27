TOTAL_COMMITS=600

echo "Will create $TOTAL_COMMITS commits..."

for ((i = 1; i <= TOTAL_COMMITS; i++)); do
  echo "Commit #$i - $(date) - $RANDOM" >> spamlog.txt
  git add spamlog.txt
  COMMIT_MSG="Auto commit $RANDOM"
  git commit -m "$COMMIT_MSG"
  sleep 0.1
done

echo "Pushing all commits..."
git push origin main
